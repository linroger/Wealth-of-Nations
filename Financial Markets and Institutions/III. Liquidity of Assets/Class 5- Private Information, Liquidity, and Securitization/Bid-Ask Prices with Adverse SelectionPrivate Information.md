---
linter-yaml-title-alias: 'Lecture Notes: Bid-Ask Prices with Adverse Selection/Private
  Information'
title: 'Lecture Notes: Bid-Ask Prices with Adverse Selection/Private Information'
tags:
  - adverse_selection
  - bid_ask_spread
  - liquidity
  - market_makers
  - private_information
aliases:
  - Adverse Selection
  - Bid-Ask
  - Information Asymmetry
  - Market Microstructure
key_concepts:
  - Bid-ask spread
  - Informed traders
  - Liquidity traders
  - Market maker behavior
  - Price adjustment
  - Private information impact
---

# Bid-Ask Prices with Adverse SelectionPrivate Information

## I. Introduction to Liquidity
- **Definition of Liquidity**:
  - Many definitions exist,  but all share a common theme:
	- Trading an asset too much or too quickly incurs costs if the asset is illiquid.

## II. The Setup
- **Traders**:
  - Two types: informed and uninformed (liquidity traders).
  - All traders and market makers are risk-neutral,  so there is no risk premium.

### A. Information Structure
1. **Private Information**:
   - Informed traders know exactly what the firm will be worth on a fixed future date.
   - Let $V$ be the unknown value; everyone knows $V$ will be either 0 or 1,  and informed traders know which value will occur.
   - Uninformed liquidity traders believe the probability that $V = 1$ is $\frac{1}{2}$.

   $$ 
   \begin{array}{c|c}
   \text{Probability} & \text{Value} \\
   \hline
   \frac{1}{2} & 1 \\
   \frac{1}{2} & 0 \\
   \end{array} 
   $$

1. **Trading Assumptions**:
   - At each instant,  at most one trade occurs; all trades are the same size.
   - This abstracts from block trading.

### B. Trading Behavior
1. **Informed Traders**:
   - Buy when the stock is underpriced at the ask,  sell when overpriced at the bid,  and do nothing if the value is between the bid and ask.
1. **Liquidity Traders**:
   - Buy when they have excess liquidity and sell when they need liquidity.
   - Half of all liquidity traders buy and the other half sell,  with each liquidity trader buying with probability $\frac{1}{2}$.

1. **Market Maker Behavior**:
   - Market makers earn zero monopoly profits and break even on average across trades.
   - They do not observe the private information of informed traders,  leading to potential losses when trading with informed traders.

## III. Pricing Mechanics
1. **Setting Prices**:
   - Market makers set prices first; traders then choose the type of trade at the fixed price.
   - To break even,  market makers set a bid-ask spread.
   - This means the average loss to informed traders equals the average profit from liquidity-motivated trades.

1. **Break-even Conditions**:
   - The bid is the expected value of the stock given public information and the fact that a sell order arrives.
   - The ask is the expected value given all public information and the fact that a buy order arrives.

### A. Example Without Informed Traders
- If there are no informed traders,  the [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] is zero.
- If there are only informed traders,  there is no spread allowing the market maker to break even.

## IV. One Period Example
1. **Absence of Trades**:
   - The stock price would be $\frac{1}{2}$ due to the $50-50$ chance of being worth $1$ or $0$.

1. **Trading Orders**:
   - When an order comes in,  the probability it is informed is $\frac{1}{2}$.

### A. Determining the Ask Price
1. If a buy order comes in from an informed trader:
   - The private information indicates the stock is worth $1$.
   - The market maker's profit:
	 $$
     \text{Profit} = \text{ask} - 1
     $$
1. If the buy is from a liquidity trader:
   - The average profit from the trade:
	 $$
     \text{Profit} = \text{ask} - \left( \frac{1}{2} \cdot 1 + \frac{1}{2} \cdot 0 \right) = \text{ask} - \frac{1}{2}
     $$

1. **Break-even Calculation**:
   - Average profit is zero when:
	 $$
     \frac{1}{2} \cdot (\text{ask} - 1) + \frac{1}{2} \cdot \left( \text{ask} - \frac{1}{2} \right) = 0
     $$
   - Solving gives:
	 $$
     \text{ask} = \frac{3}{4}
     $$

### B. Determining the Bid Price
1. If a sell order comes from an informed trader:
   - The private information indicates the stock is worth $0$.
   - The market maker's profit:
	 $$
     \text{Profit} = 0 - \text{bid}
     $$
1. If the sell is from a liquidity trader:
   - The average profit from the trade:
	 $$
     \text{Profit} = \frac{1}{2} - \text{bid}
     $$

1. **Break-even Calculation**:
   - Average profit is zero when:
	 $$
     \frac{1}{2} \cdot (0 - \text{bid}) + \frac{1}{2} \cdot \left( \frac{1}{2} - \text{bid} \right) = 0
     $$
   - Solving gives:
	 $$
     \text{bid} = \frac{1}{4}
     $$

## V. Implications of Private Information
1. **Price Adjustment**:
   - Private information reduces liquidity.
   - The larger the fraction of informed traders,  the larger the bid-ask spread,  but the quicker the price reflects private information.
   - Buying or selling a security will move the price,  even without information in a competitive market.

1. **Market Efficiency**:
   - Market efficiency allows trading profits with private information,  although it can be hard to determine if one possesses truly private information.

## VI. Graphical Representation

```latex
\begin{document}
\usetikzlibrary{positioning}
\begin{tikzpicture}[node distance=2cm]
    \node (start) at (0, 0) {};
    \node[above=of start] (p1) {$\frac{1}{2}$};
    \node[above right=of start] (ask) {Initial Ask=$\frac{3}{4}$};
    \node[above right=of ask] (p2) {$\frac{9}{10}$};
    \node[below=of start] (p3) {$\frac{1}{2}$};
    \node[below right=of start] (bid) {Initial Bid=$\frac{1}{4}$};
    \node[below right=of bid] (p4) {$\frac{1}{10}$};
    \draw[->] (p1) -- (ask);
    \draw[->] (ask) -- (p2);
    \draw[->] (p3) -- (bid);
    \draw[->] (bid) -- (p4);
    \draw[->] (start) -- (p1);
    \draw[->] (start) -- (p3);
\end{tikzpicture}
\end{document}
```

```latex
\documentclass{standalone}
\usepackage{tikz}
\usetikzlibrary{arrows.meta,  positioning}

\begin{document}
\begin{tikzpicture}[node distance=1.5cm,  >=Stealth]
    % Define nodes
    \node (start) at (0, 0) {};
    \node[above left=of start] (p1) {$\frac{1}{2}$};
    \node[above right=of start] (ask) {Initial Ask=$\frac{3}{4}$};
    \node[right=of ask] (p2) {$\frac{9}{10}$};
    \node[below left=of start] (p3) {$\frac{1}{2}$};
    \node[below right=of start] (bid) {Initial Bid=$\frac{1}{4}$};
    \node[right=of bid] (p4) {$\frac{1}{10}$};

    % Draw arrows
    \draw[->] (p1) -- (ask);
    \draw[->] (ask) -- (p2);
    \draw[->] (p3) -- (bid);
    \draw[->] (bid) -- (p4);
    
    % Additional lines for aesthetics
    \draw[->] (start) -- (p1);
    \draw[->] (start) -- (p3);
\end{tikzpicture}
\end{document}
```

## VII. Results of the Model
- **Summary**:
  - Private information creates a bid-ask spread.
  - The price adjusts to reflect new information from informed traders.
  - Informed trading leads to price changes even in competitive markets.