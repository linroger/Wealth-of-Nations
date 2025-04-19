---
LLM-tagged: 2025-03-10 14:12:46.154000+00:00
tags:
  - agency_problems
  - asset_services
  - bond_covenants
  - borrower_lender_conflicts
  - capital_markets
  - debt_incentives
aliases:
  - Borrower-Lender Conflicts
  - Class Note 1 Borrower-Lender conflicts and implied agency problems
  - Debt and Incentives
key_concepts:
  - Asset services reduce bad effects
  - Bond covenants and borrower behavior
  - Debt common for smaller firms
  - Debt distorts capital budgeting
  - Incentives of equity holders
  - Risky debt and lender advantage
---

Here is a tagged summary:

**Key Takeaways**

* Debt can distort capital budgeting decisions and provide perverse incentives to the firm.
* Risky debt provides an advantage to the lender, but can lead to monitoring problems.
* Bond covenants may not be effective in preventing bad behavior by the borrower if they are not enforceable or contain too little detail.

**Question A: Reducing Bad Effects of Debt**

* Bond covenants may not be sufficient to prevent bad behavior by the borrower.
* Enforcement requires effort and monitoring, which can be difficult with many small bondholders.
* The lender needs to have substantial bargaining power over the borrower to renegotiate contracts.

**Question B: Asset Services and Their Role in Reducing Bad Effects**

* Asset services of banks and other intermediaries are important because they provide a single point of contact for borrowers and lenders, making it easier to monitor and enforce contracts.
* This can help reduce monitoring problems and make bond covenants more effective.

**Question C: Why is Debt Common, Especially for Smaller Firms?**

* Debt may be common for smaller firms because they have limited access to capital markets or face higher costs of borrowing.
* Asset services of banks and other intermediaries may play a role in making debt more accessible and manageable for small firms.

---

---
aliases:
- Class Note 1 Borrower-Lender conflicts and implied agency problems.md
- Class Note 1 Borrower-Lender conflicts and implied agency problems
tags:
- 
- 
title: Class Note 1 Borrower-Lender conflicts and implied agency problems
---
# Class Note 1 Borrower-Lender conflicts and implied agency problems

The amount of leverage has an impact on the incentives of someone who maximizes the value of the residual equity claim. This“asset substitution theory”is a popular theory of capital structure,  but it is not too plausible for large firms. It makes the most sense for owner-managed firms,  where the manager is the stockholder. If the owner and manager differ,  one needs to examine the manager's incentive contract to learn his/her incentives. We will see later that the owner's and manager's incentives are naturally aligned for nearly insolvent firms and for some financial institutions that have government deposit insurance.
The example illustrates how divided ownership of different parts of the cash flow distribution. distorts capital budgeting decisions.
Debt holders own the lower tail of the distribution of firm value,  and equity owners the upper tail. This is the cause of the conflict of interest because some decisions hurt the lower tail and help the upper tail (and can help or hurt the overall value of the firm).

### 1. No debt

Two projects,  the riskier one also has a lower expected return. Each has only two possible outcomes,  one if a depression (D),  one if prosperity P). The probability of each outcome is 1/2 Each project requires the an initial outlay of $\$800$

```latex
\usepackage{amsmath}
\begin{document}
\centering
\begin{tabular}{|c|c|c|c|c|}
\hline
Project & Value in D & Value in P & Expected Value & Expected Return \\ 
\hline
1       & 500        & 1500       & 1000           & $\frac{200}{800} = 25\%$ \\ 
\hline
2       & 0          & 1551       & 775.5          & $\frac{-24.5}{800} = -3.06\%$ \\ 
\hline
\end{tabular}
\end{document}
```

We could get fancy and use the states model to take account of the positive"beta"of each project (each pays off more in prosperity). Project 2 has a higher beta,  implying that it should require a higher discount rate than project 1. It is sufficient for our purposes to use the expected returns to see the incentive problem with debt.
Clearly,  project 1 is the best investment. An owner-managed firm with no debt would select it,  . since all require the same initial outlay.

 1. What about a firm with debt with face $s=600$ in place?
	- The fixed payment of $\$600$ is a sunk cost.If thefirm is going to default, thenit doesnot care"how big" the default is.It wants tomake more when not in default. Cash flows to equity when debt of $\$600$ is in place

	```latex
\begin{document}
\begin{tabular}{|c|c|c|c|}
\hline
Project & Cash Flow if D & Cash Flow if P (Debt = 600) & Expected Value \\ \hline
1 & 0 & 1500 - 600 = 900 & 450 \\ \hline
2 & 0 & 1551 - 600 = 951 & 475.5 \\ \hline
\end{tabular}
\end{document}
```

The levered firm would select project number 2,        despite its lower net present value,        because it has a higher present value conditional on not leading to bankruptcy. The equity owner owns the upper tail, and is only concerned with the returns he owns. Note that no matter how the equity owner values the cash flows if P, he prefers project 2 since both have identical cash flows if D and project 2 has higher payments if P.
This does not mean that firms"want" to go bankrupt. Instead, it is a statement about debt capacity. If the [[Leverage Ratio|leverage ratio]] gets too high, then these perverse incentive effects of debt increase. This can lead the firm to tilt its decisions toward excessively risky projects, with a lower net present value. Potential bondholders can put themselves into the owner's shoes, and take this into account when deciding what interest rate to charge on the bond. The lender can predict what the borrower will do, but there is a problem because the lender cannot directly observe the project choice. What is the debt capacity of the firm? What is the highest face value, F, that the borrower prefers project 1?
The borrower's equity payoff from Project 1 and 2 with debt of face F is:

```latex
\begin{document}
\renewcommand{\arraystretch}{1.5} % Adjust the height for better spacing
\begin{tabular}{|c|c|c|}
\hline
\textbf{Project} & \textbf{Condition} & \textbf{Equity Payoff} \\ \hline
\textbf{Project 1 (Face F)} & \(F \leq 500\)  & \(\frac{1}{2}(1500 - F) + \frac{1}{2}(500 - F) = 1000 - F\) \\ \cline{2-3}
  & \(500 < F \leq 1500\) & \(\frac{1}{2}(1500 - F)\) \\ \cline{2-3}
  & \(F > 1500\)    & 0 \\ \hline
\textbf{Project 2 (Face F)} & \(F < 1551\)    & \(\frac{1}{2}(1551 - F)\) \\ \cline{2-3}
  & \(F > 1551\)    & 0 \\ \hline
\end{tabular}
\end{document}
```

 The debt capacity must be less than 500,  because if the firm will certainly default in Depression,  all that matters is what it is worth in Prosperity.

- For $F<500$,  Project 1 is preferred for all F that satisfy $\geq$ 21000 - F $\geq$ 1/2(1551 -F),  which solves out to $F\leq 449$.
- As a result,  449 is the debt capacity in face value.
- Suppose lenders require an expected return of $r$ for investing in any security of the firm. If the firm issued debt with face value 448 debt,  it would choose Project 1,  and then the debt could raise up to $\frac{448}{1+r}$ Prj lender if it does not help himself.)If the firm issued debt with face $F>449$,  it would lead to project an increase $\frac{1/2\mathrm{F}\:+\:1/2(0)}{1+\mathrm{r}}$.
- Risky debt (debt with a positive probability of bankruptcy) distorts capital budgeting decisions. It provides incentives to make tradeoffs between cash in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] and not in [[Course Notes/HBR Notes/A Strategic Perspective on Bankruptcy|bankruptcy]] that differ from the ones that maximize the value of the firm.
- The potential bondholders will require a high enough interest rate to give themselves a competitive rate of return,  for example,  $10\%$. Thus,  any reductions in the value of the capital budgeting program of the firm will come out of the owner's pockets. If the firm selected too high a leverage ration,  it would be giving itself a perverse incentive contract. It would not do this in the first place if it had alternatives. Thus,  we might not expect a firm to choose a capital structure with as much debt as our example if it faced an unobservable choice between these projects.
- This leaves us with some unanswered questions: A. How can these bad effects of debt be reduced? B. How do bank asset services help reduce these bad effects? C. If debt is so bad,  why is it so common,  especially for smaller firms? Why not use another financial contract?

Beginning with question a,  we examine problems with bond covenants,  contractual provisions in bond or loan indentures. See the Wruck paper in the packet for a description of typical covenants.

- Just prohibiting an action in a bond covenant does not prevent it from happening. The lender needs to know about the violation before it happens or soon thereafter. In addition,  the lender must have some bargaining power over the borrower in order to stop a "crime in progress.”
- Enforcement requires effort and monitoring of the borrower. Without substantial monitoring,  the contract cannot depend on anything except the grossest public information.
- If not all contingencies are spelled out,  contracts must be renegotiated over time. This too requires the lender to have lots of information about the borrower's situation.
- If the lender is not one individual but many small bondholders,  the [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] can be difficult to enforce. There can be either duplication of effort if each lender monitors the situation carefully or more likely,  a"free rider" problem,  where none of the small bondholders find it worthwhile to bother to monitor. Without monitoring,  [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will not be renegotiated or contain much detail. If there is no monitoring,  [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] will be written contingent only on the grossest public information.
- This gives an advantage to having a single lender,  rather than many lenders. We will see that this is a part of the argument why asset services of banks and other intermediaries are important.
- The US Federal Trust Indenture Act prohibits majority voting to restructure debt contracts that reduce principal or interest or extend the debt maturity. A $100% vote is required to change these "key covenants." Thus,  even if public bondholders had the information,  they probably could not use it. Changes to other [[Class Slides 2 Discussion of Loan Covenants Vs. Bond Covenants|Covenants]] in bonds require a 2/3 vote in dollar value,  and 50% measured in the fraction of bondholders (not weighted by dollar value).