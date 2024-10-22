//
//  ContentView.swift
//  JobApplicationTracker
//

import SwiftUI

struct ContentView: View {
    @EnvironmentObject var jobStore: JobStore

    var body: some View {
        TabView {
            JobsView()
                .tabItem {
                    Label("Jobs", systemImage: "briefcase.fill")
                }
                .tag(0)

            StatsView()
                .tabItem {
                    Label("Stats", systemImage: "chart.bar.fill")
                }
                .tag(1)
        }
        .tint(Color.accentColor) // .accentColor replaced with .tint for modern SwiftUI
    }
}


//
//  JobsView.swift
//  JobApplicationTracker
//

import SwiftUI

struct JobsView: View {
    @EnvironmentObject var jobStore: JobStore
    @State private var searchText = ""
    @State private var showingAddJob = false

    var body: some View {
        NavigationView {
            SidebarView(selectedJob: $jobStore.selectedJob, searchText: $searchText)
                .environmentObject(jobStore)

            if let job = jobStore.selectedJob {
                JobDetailView(job: job)
                    .environmentObject(jobStore)
            } else {
                Text("Select a job to view details")
                    .foregroundColor(.secondary)
            }
        }
        .toolbar {
            ToolbarItemGroup(placement: .navigationBarLeading) {
                #if os(iOS)
                EditButton()
                #endif
            }
            ToolbarItemGroup(placement: .navigationBarTrailing) {
                Button(action: { jobStore.isAddingNewJob = true }) {
                    Image(systemName: "plus")
                }
                .sheet(isPresented: $jobStore.isAddingNewJob) {
                    AddJobView(isPresented: $jobStore.isAddingNewJob)
                        .environmentObject(jobStore)
                }
            }
        }
        .onAppear {
            if jobStore.jobApplications.isEmpty {
                jobStore.loadJobs()
            }
        }
    }
}


//
//  StatsView.swift
//  JobApplicationTracker
//

import SwiftUI
import ContributionChart

struct StatsView: View {
    @EnvironmentObject var jobStore: JobStore
    
    // Chart dimensions
    let rows = 7
    let columns = 14
    
    // Generate chart data from job applications
    var chartData: [Double] {
        let applicationsByDate = jobStore.applicationsCountByDate()
        let calendar = Calendar.current
        let today = calendar.startOfDay(for: Date())
        
        // We want data for the last 'rows * columns' days
        var data = [Double]()
        
        for dayOffset in (0..<(rows * columns)).reversed() {
            let date = calendar.date(byAdding: .day, value: -dayOffset, to: today)!
            let applicationCount = applicationsByDate[date] ?? 0
            data.append(Double(applicationCount))
        }
        
        return data
    }

    var body: some View {
        ScrollView {
            VStack(alignment: .leading, spacing: 20) {
                Text("Statistics")
                    .font(.largeTitle)
                    .bold()
                    .padding(.top)

                Text("Total Applications: \(jobStore.jobApplications.count)")
                    .font(.title2)

                Text("Applications by Status:")
                    .font(.title3)
                    .padding(.top)

                ForEach(JobStatus.allCases, id: \.self) { status in
                    Text("\(status.rawValue): \(jobStore.jobApplications.filter { $0.status == status }.count)")
                }

                Spacer()

                // Contribution Chart Section
                Text("Job Application Activity Heatmap")
                    .font(.title3)
                    .padding(.top)
                
                ContributionChartView(
                    data: chartData,
                    rows: rows,
                    columns: columns,
                    targetValue: 5.0, // Adjust based on expected application max per day
                    blockColor: .green // Use green blocks
                )
                .frame(height: 200) // Adjust the height as needed
                .padding()
                
                Spacer()
            }
            .padding()
            .navigationTitle("Stats")
        }
    }
}


//
//  AddJobView.swift
//  JobApplicationTracker
//

import SwiftUI
import UniformTypeIdentifiers

struct AddJobView: View {
    @EnvironmentObject var jobStore: JobStore
    @Binding var isPresented: Bool
    @StateObject private var viewModel = JobViewModel()
    @State private var isImporting: Bool = false
    @State private var importedDocuments: [JobDocument] = []
    @State private var locations: [String] = ["New York City, NY", "Los Angeles, CA", "Chicago, IL"]
    @State private var showAddLocationSheet = false

    var body: some View {
        #if os(macOS)
        macOSBody
        #else
        iOSBody
        #endif
    }

    var macOSBody: some View {
        VStack {
            Text("ADD NEW JOB")
                .font(.title2)
                .bold()
                .padding()

            ScrollView {
                content
            }
            .padding()

            HStack {
                Button(action: {
                    isPresented = false
                }) {
                    Label("Cancel", systemImage: "xmark.circle.fill")
                }
                Spacer()
                Button(action: {
                    addJob()
                    isPresented = false
                }) {
                    Label("Add", systemImage: "checkmark.circle.fill")
                }
                .disabled(!viewModel.isInputValid)
            }
            .padding()
        }
        .frame(width: 500, height: 600)
        .sheet(isPresented: $showAddLocationSheet) {
            NewLocationView(locations: $locations, selectedLocation: $viewModel.location)
        }
    }

    var iOSBody: some View {
        NavigationView {
            ScrollView {
                content
            }
            .navigationTitle("Add New Job")
            .toolbar {
                ToolbarItem(placement: .navigationBarLeading) {
                    Button("Cancel") {
                        isPresented = false
                    }
                }
                ToolbarItem(placement: .navigationBarTrailing) {
                    Button("Add") {
                        addJob()
                        isPresented = false
                    }
                    .disabled(!viewModel.isInputValid)
                }
            }
        }
        .sheet(isPresented: $showAddLocationSheet) {
            NewLocationView(locations: $locations, selectedLocation: $viewModel.location)
        }
    }

    private var content: some View {
        VStack(alignment: .leading, spacing: 15) {
            // Job Details Section
            SectionView(title: "Job Details") {
                Group {
                    TextField("Company Name", text: $viewModel.companyName)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                    TextField("Job Title", text: $viewModel.jobTitle)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                }
            }

            // Application Details Section
            SectionView(title: "Application Details") {
                Group {
                    TextField("Link to Job", text: $viewModel.linkToJob)
                        .textFieldStyle(RoundedBorderTextFieldStyle())

                    Picker("Application Status", selection: $viewModel.status) {
                        ForEach(JobStatus.allCases, id: \.self) { status in
                            Text(status.rawValue).tag(status)
                        }
                    }
                    .pickerStyle(MenuPickerStyle())

                    // Location Picker
                    Picker("Location", selection: $viewModel.location) {
                        ForEach(locations, id: \.self) { location in
                            Text(location).tag(location)
                        }
                        Text("Add New Location")
                            .tag("Add New Location")
                    }
                    .onChange(of: viewModel.location) { newValue in
                        if newValue == "Add New Location" {
                            viewModel.location = ""
                            showAddLocationSheet = true
                        }
                    }

                    DatePicker("Application Date", selection: $viewModel.dateOfApplication, displayedComponents: .date)
                        .datePickerStyle(GraphicalDatePickerStyle())
                }
            }

            // Documents Section
            SectionView(title: "Documents") {
                Group {
                    if !importedDocuments.isEmpty {
                        ScrollView(.horizontal) {
                            HStack {
                                ForEach(importedDocuments) { document in
                                    Text(document.fileName)
                                        .padding(5)
                                        .background(Color.blue.opacity(0.2))
                                        .cornerRadius(5)
                                }
                            }
                        }
                    }

                    Button("Upload Documents") {
                        isImporting = true
                    }
                }
            }

            // Job Description Section
            SectionView(title: "Job Description") {
                ResizableTextEditor(text: $viewModel.jobDescription)
                    .frame(minHeight: 150)
            }

            // Cover Letter Section
            SectionView(title: "Cover Letter") {
                ResizableTextEditor(text: $viewModel.coverLetter)
                    .frame(minHeight: 150)
            }

            // Notes Section
            SectionView(title: "Notes") {
                ResizableTextEditor(text: $viewModel.notes)
                    .frame(minHeight: 150)
            }
        }
        .padding()
        .fileImporter(
            isPresented: $isImporting,
            allowedContentTypes: [.item],
            allowsMultipleSelection: true,
            onCompletion: handleFileImport
        )
    }

    private func addJob() {
        viewModel.addJob(to: jobStore, documents: importedDocuments)
    }

    private func handleFileImport(result: Result<[URL], Error>) {
        do {
            let urls = try result.get()
            for url in urls {
                let data = try Data(contentsOf: url)
                let document = JobDocument(fileName: url.lastPathComponent, fileData: data)
                importedDocuments.append(document)
            }
        } catch {
            print("Failed to import files: \(error.localizedDescription)")
        }
    }
}


//
//  JobStore.swift
//  JobApplicationTracker
//

import Foundation
import SwiftUI

class JobStore: ObservableObject {
    @Published var jobApplications: [JobApplication] = []
    @Published var isAddingNewJob = false
    @Published var isEditingJob = false
    @Published var selectedJob: JobApplication?

    init() {
        loadJobs()
    }

    // Group applications by date and return the count for each date
    func applicationsCountByDate() -> [Date: Int] {
        var applicationsByDate = [Date: Int]()

        // Group and count applications by the date of application
        for job in jobApplications {
            let date = Calendar.current.startOfDay(for: job.dateOfApplication) // Normalize to day
            applicationsByDate[date, default: 0] += 1
        }
        
        return applicationsByDate
    }

    func createJob(with job: JobApplication) {
        jobApplications.append(job)
        saveJobs()
    }

    func editJob(with updatedJob: JobApplication) {
        if let index = jobApplications.firstIndex(where: { $0.id == updatedJob.id }) {
            jobApplications[index] = updatedJob
            saveJobs()
        }
    }

    func deleteJob(for id: UUID) {
        jobApplications.removeAll { $0.id == id }
        saveJobs()
    }

    func loadJobs() {
        guard let savedData = UserDefaults.standard.data(forKey: "jobs") else {
            return
        }
        do {
            jobApplications = try JSONDecoder().decode([JobApplication].self, from: savedData)
        } catch {
            print("Failed to load jobs: \(error.localizedDescription)")
        }
    }

    func saveJobs() {
        do {
            let data = try JSONEncoder().encode(jobApplications)
            UserDefaults.standard.set(data, forKey: "jobs")
        } catch {
            print("Failed to save jobs: \(error.localizedDescription)")
        }
    }
}