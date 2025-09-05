# GO-takehomepaycalc

## Why I did this
I'm learning Go, and also looking at taking my first contect to perm position (Yes, I know I've been in the industry for a long time and never taken a contract to perm position...). 

What I did. 





## Assumptions

I had to make some asumptions, and still need ot check if they are correct. 

* Pay Frequency: The program will allow selecting weekly (52 pay periods), biweekly (26), semi-monthly (24), or monthly (12) pay frequencies to annualize income for withholding calculations.
* Dependents/Filing Status: The program will accept filing status (Single, Married Filing Jointly, Head of Household) and number of dependents (children under 17 and other dependents) to adjust federal withholding.
* Pre-Tax Deductions: Kept as in your example (Medical: 13.24%, Dental: 0.45%, Vision: 0.07%, others 0%) for consistency, but you can modify them in the JSON input.
* Gross Pay: Your example used $4,200, so I'll assume an hourly rate and hours worked to achieve this (e.g., $52.50 × 80 hours weekly). You can adjust these in the input.


**TO DO LIST**
- [ ] Check assumptions ;-) 


