---
tags:
  - cash_flows
  - financial_engineering
  - financial_instruments
  - replication
  - synthetic_instruments
aliases:
  - Chapter 3.1
  - Intro
  - Introduction to Financial Engineering
key_concepts:
  - Cash flows and instruments
  - Contractual equation method
  - Forward rate agreements
  - Replicating cash flows
  - Synthetic instrument creation
---

# 3.1 INTRODUCTION  

All financial instruments can be visualized as bundles of cash flows. They are designed so that. market participants can trade cash flows that have different characteristics and different risks. This chapter uses interest rate forwards and futures to discuss how cash flows can be replicated and then repackaged to create synthetic instruments.  

It is easiest to determine replication strategies for linear instruments. We show that this can be further developed into an analytical methodology to create synthetic equivalents of complicated instruments as well. This analytical method will be summarized by a (contractual) equation. After plugging in the right instruments, the equation will yield the synthetic for the cash flow of interest. Throughout this chapter, we assume that there is no default risk and we discuss only static replication methods. Positions are taken and kept unchanged until expiration, and require no rebalancing. Dynamic replication methods will be discussed in Chapter 8.  

This chapter develops the financial engineering methods that use forward loans, forward rate agreements (FRAs), and Eurocurrency futures. We first discuss these instruments and obtain contractual equations that can be manipulated usefully to produce other synthetics. The synthetics are used to provide pricing formulas.  
