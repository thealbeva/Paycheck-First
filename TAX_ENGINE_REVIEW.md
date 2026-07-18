2026 Tax Engine Review

Review date: 2026-07-17

## Conclusion

The current tax engine is suitable only as a rough planning estimate. It is not ready to be presented as a comprehensive 2026 paycheck withholding calculator.

Every state has an explicit rate rule, but explicit coverage is not the same as accurate tax calculation. The engine currently applies most state rates to an incorrect taxable-income base and cannot represent filing status, dependents, credits, recapture rules, or many state-specific adjustments.

## Confirmed correctness problems

### Federal brackets are stale

The app labels its federal configuration as 2026 but uses these single-filer thresholds:

- $11,925
- $48,475
- $103,350
- $197,300
- $250,525
- $626,350

Those are not the finalized 2026 thresholds. The IRS 2026 single-filer thresholds are:

- $12,400
- $50,400
- $105,700
- $201,775
- $256,225
- $640,600

The app's $16,100 federal standard deduction is correct for a single filer in 2026.

### State taxable income is modeled incorrectly

The engine currently calculates state taxable income as annual gross income minus selected pre-tax contributions, then applies a state rate schedule.

It does not apply state standard deductions, personal exemptions, dependent exemptions, credits, income-based phaseouts, or state-specific additions and subtractions. This can materially overstate or understate state tax.

Example: Minnesota's 2026 single standard deduction is $15,300, but the current state calculation does not subtract it.

### 2026 state-rate audit completed

All 50 state entries were compared with the published 2026 single-filer rate table on July 14, 2026. Stale schedules were corrected for California, Delaware, Hawaii, Maine, Massachusetts, Minnesota, New Jersey, New Mexico, New York, Vermont, West Virginia, and Wisconsin. The nine states without a broad wage income tax remain configured with no wage income tax.

This verifies statutory rates and bracket boundaries only. It does not make the calculated state amount equivalent to a completed state return or an employer's withholding calculation because the simplified engine still omits many state deductions, exemptions, credits, recapture rules, and local taxes.

### Filing-status scenarios are now available but remain simplified

The app now collects filing status and supports federal planning scenarios including head of household and self-employment income. This removes the previous single-filer-only interface limitation, but it does not make the estimate equivalent to a filed return. State rules remain simplified and may not vary deductions, exemptions, credits, or brackets correctly for every filing status.

### Paycheck withholding is not the same as annual tax liability

The engine estimates annual income-tax liability and divides it by the number of paychecks. Employer withholding generally follows IRS Publication 15-T and state withholding methods, which incorporate payroll-period tables, W-4 elections, adjustments, credits, and additional withholding.

The current result is a planning estimate, not a prediction of the exact withholding shown on a paycheck.

### FICA is incomplete at higher incomes

The Social Security rate and 2026 wage base are represented, and the regular Medicare rate is represented. The Additional Medicare Tax applicable above the federal threshold is not currently modeled.

### Tips and variable income need marginal recalculation

Tracked wages, overtime, tips, and other income are currently converted to net using an effective net-to-gross ratio derived from the static income estimate. This is convenient but does not recalculate marginal federal, state, Social Security, Medicare, or withholding effects as variable income changes.

### State-specific behavior is missing

The current rule types support only:

- No wage income tax
- One flat rate
- Basic progressive brackets

They cannot accurately represent features such as:

- Standard deductions and personal exemptions
- Tax credits used instead of deductions
- Income-dependent deduction phaseouts
- High-income benefit recapture
- State-specific federal conformity adjustments
- Local and county income taxes
- Special handling of retirement, tips, or other income

## Test coverage gaps

Current state-tax tests cover a no-tax state, Minnesota, and Wisconsin. They validate the simplified bracket calculation but do not validate state deductions or withholding tables.

Each supported state needs tests at multiple income levels, including bracket boundaries, plus a source citation and tax-year identifier.

## Recommended rebuild

### Required inputs

- Filing status (implemented for federal planning; state-specific treatment still requires expansion)
- Dependents or applicable exemption count
- Pay frequency
- W-4 adjustments or a clearly labeled simplified mode
- State
- Optional locality when local income tax support is added

### Required rule model

Each state configuration should support:

- Tax year and source metadata
- Filing-status-specific brackets
- Standard deduction
- Personal and dependent exemptions
- Credits and phaseouts where material
- State additions and subtractions supported by the app
- Explicit unsupported-rule notes

### Calculation modes

The app should distinguish:

1. **Paycheck withholding estimate** using federal and state payroll-withholding methods.
2. **Annual tax estimate** using annual liability rules.
3. **Actual take-home override** from the user's pay statement, which remains the best budgeting input.

### Verification standard

- Use IRS publications for federal rules.
- Use each state's revenue or taxation department as the primary source.
- Record source URL, effective tax year, and last verification date with every configuration.
- Add automated coverage ensuring every state has a rule and official-source tests.
- Reverify the full dataset annually before changing the active tax year.

## Safe interim presentation

Until the rebuild is complete:

- Label results as rough estimates.
- State that filing-status scenarios remain simplified and that state-specific treatment may be incomplete.
- Keep 2026 income / 2027 filing-year labeling visible.
- State that state deductions, credits, local taxes, and special rules may be omitted.
- Continue prioritizing an entered actual take-home paycheck over calculated income.
- Do not claim the result predicts the user's exact paycheck or tax liability.
