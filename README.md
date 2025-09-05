# GO-takehomepaycalc

## Why I did this
I'm learning Go, and also looking at taking my first contect to perm position (Yes, I know I've been in the industry for a long time and never taken a contract to perm position...). 

What I did. 





## Assumptions

I had to make some asumptions, and still need ot check if they are correct. 
* Pay Frequency: The program already supports Weekly (52 periods), Biweekly (26), SemiMonthly (24), and Monthly (12). I'll calculate weekly amounts by dividing by the number of weeks per period (1 for Weekly, 2 for Biweekly, ~2.17 for SemiMonthly, ~4.33 for Monthly).
* Dependents/Filing Status: The program will accept filing status (Single, Married Filing Jointly, Head of Household) and number of dependents (children under 17 and other dependents) to adjust federal withholding.
* Pre-Tax Deductions: Kept as in your example (Medical: 13.24%, Dental: 0.45%, Vision: 0.07%, others 0%) for consistency, but you can modify them in the JSON input.
* Gross Pay: Your example used $4,200, so I'll assume an hourly rate and hours worked to achieve this (e.g., $52.50 × 80 hours weekly). You can adjust these in the input.
* Weekly Gross Pay: This is the gross pay for a single week, calculated as hourly_rate * hours_worked. For your example ($4,200 gross, $52.50/hour × 80 hours), this is straightforward if weekly, but if the input pay frequency is biweekly (e.g., 2 weeks), I'll divide the gross by the number of weeks in the pay period.
* Weekly Net Pay: This is the take-home pay per week, calculated as the paycheck's net pay (takeHomeAmount) divided by the number of weeks in the pay period. For example, if biweekly net pay is $5,482 for 2 weeks, weekly net pay is $5,482 ÷ 2 = $2,741.
* Output: Add lines at the top of the output for "Weekly Gross Pay" and "Weekly Net Pay" in dollars, before the detailed breakdown.
* Existing Features: Retain 2025 federal tax brackets, FICA rates (6.2% Social Security up to $176,100, 1.45% Medicare), Tennessee’s 0% state income tax (variable for other states), W-4 dependent adjustments, and pre-tax deductions from your example.


**TO DO LIST**
- [ ] Check assumptions ;-) 



### Testing

To test the API I am using a static json file and a curl command

``` json
{
  "hourly_rate": 52.50,
  "hours_worked": 80,
  "pay_frequency": "Weekly",
  "filing_status": "Single",
  "dependents_under_17": 2,
  "other_dependents": 0,
  "taxes": {
    "federal_income": 0,
    "state_income": 0.0,
    "local_income": 0.0
  },
  "fica": {
    "social_security": 0,
    "medicare": 0,
    "state_disability_insurance_tax": 0.0,
    "state_unemployment_insurance_tax": 0.0,
    "state_family_leave_insurance_tax": 0.0,
    "state_workers_compensation_insurance_tax": 0.0
  },
  "pre_tax_deductions": {
    "medical_insurance": 0.1324,
    "dental_coverage": 0.0045,
    "vision_insurance": 0.0007,
    "401k": 0.0,
    "long_term_disability_insurance": 0.0,
    "life_insurance": 0.0,
    "commuter_plan": 0.0,
    "fsa": 0.0,
    "hsa": 0.0
  },
  "post_tax_deductions": 0.0
}
```

