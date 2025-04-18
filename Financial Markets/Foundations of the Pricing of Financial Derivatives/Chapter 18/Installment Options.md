---
tags:
  - bond_loan
  - compound_option
  - installment_options
  - numerical_solution
  - option_pricing
aliases:
  - Compound Option
  - Installment
  - Installment Option
key_concepts:
  - Exercise at installment date
  - Installment option variation
  - Multiple underlying options
  - Numerical iterative solution
  - Premium spread over time
---

# 18.8 INSTALLMENT OPTIONS

A variation of the compound option is the installment option. This is an option in which the premium is spread out in equal amounts over time. At each installment date, the holder of the option decides whether to exercise it, thereby paying the installment premium and continuing with the option. If the holder prefers not to continue, they simply fail to pay the installment. The option then terminates.11 This instrument is very much like the compound. option except that there are typically several installments, necessitating a more complex option pricing model requiring the evaluation of higher-order multivariate normal probability distributions. Also, the installments, which correspond to the exercise prices of the multiple underlying options, are usually all equal. Solving the pricing equation is quite difficult and usually requires a numerical iterative solution. The installment option permits. the holder to change their mind later and get out of the contract by simply failing to pay. later installments. All previously paid installments are, of course, forgone..

Finally, it should be noted that a bond or loan with multiple payments is somewhat like an installment option. At each payment date, the borrower decides whether to pay off, which is like deciding to make an installment payment. For more information, see Merton (1974) and Geske (1977, 1984). Once default occurs, the sequence of installment payments ends.
