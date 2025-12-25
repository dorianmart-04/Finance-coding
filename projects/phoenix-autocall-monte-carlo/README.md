# Phoenix Autocall – Monte Carlo Pricing

## Objective
Implement a simple Monte Carlo pricing of a Phoenix Autocall structured product,
by simulating underlying price paths and applying the rules for automatic recall,
coupon payments with memory effect, and capital protection.

## Methodology
- Simulation of underlying price paths using a Geometric Brownian Motion (GBM)
- Barrier checks at each observation date:
  - autocall barrier
  - coupon barrier with memory effect
- Discounting of cash flows
- Capital repayment at maturity with a protection barrier (PDI)

## Technologies
- Python
- numpy

## Results
- Monte Carlo price of the product
- Monte Carlo standard error
- Computation time




