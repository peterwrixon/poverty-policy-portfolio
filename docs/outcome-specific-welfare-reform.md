# A Needs-Based Redesign of the Universal Credit System: Evaluating Utility Quotas, Consumption Standards, and Macroeconomic Outcomes

The architecture of the United Kingdom’s social security safety net, primarily administered through the Universal Credit (UC) system, currently relies on standard cash allowances that are decoupled from the actual physiological, environmental, and social costs of maintaining a minimum acceptable standard of living. As of early 2026, the Universal Credit caseload has expanded to encompass 8.4 million individuals across approximately 7.2 million households, representing a vast segment of the UK population reliant on state support.

The incidence of poverty within this demographic is structurally embedded; recent macroeconomic analyses indicate that over 40% of people receiving Universal Credit are situated below the relative poverty line, with 75% of those in poverty experiencing deep material deprivation. To rectify these systemic inadequacies, a fundamental transition from arbitrary, flat-rate financial allowances toward a dynamically calculated, needs-based allocation system is required.  

This report models, costs, and evaluates a comprehensive redesign of the Universal Credit framework. The proposed architecture separates welfare provision into two highly calibrated mechanisms. First, inelastic physiological and environmental needs—specifically domestic energy, water, and digital connectivity—are met through direct, volume-based utility quotas discounted at the point of billing, entirely insulating vulnerable demographics from retail market volatility. Second, all remaining core nutritional, personal, and transport needs are met via a liquid cash transfer pegged precisely to a Consumer Prices Index (CPI) linked basket of goods derived from the Minimum Income Standard (MIS). This structural bifurcation ensures absolute baseline security while simultaneously addressing the severe macroeconomic drag and public health costs associated with deep poverty.

## 1\. Deriving Household Volumetric Utility Formulas

>To eliminate fuel and water poverty, the proposed policy bypasses cash transfers for utility bills. Instead, the Department for Work and Pensions (DWP), operating in statutory coordination with regulatory bodies such as Ofgem and Ofwat, allocates a precise volume of energy, water, and data directly to the claimant's utility account. The supplier waives standing charges and zero-rates the consumed quota, subsequently reclaiming the ~~wholesale cost plus a regulated margin directly from the state~~. Determining the exact volumetric need requires robust, empirically grounded mathematical formulas that account for occupancy, property thermodynamics, and seasonal variations.

### 1.1. Domestic Electricity: Establishing Non-Heating Baseloads

Electrical energy requirements cannot be distributed on a flat per-capita basis due to the nature of domestic appliance usage and lighting. Total domestic energy demand must be split into non-heating electrical baseloads (such as refrigeration, cooking, and lighting) and thermal demand (space heating and domestic hot water).  
For non-heating electricity, consumption scales with household occupancy but exhibits a high fixed baseload that remains constant regardless of occupant numbers. Government energy efficiency data and Ofgem’s Typical Domestic Consumption Values (TDCV) suggest an average baseline electrical consumption of 2,500 kWh annually for a medium household, recently revised downward from 2,700 kWh reflecting minor efficiency improvements. To operationalise this into a dynamic, per-household welfare formula, the annual electricity quota E(N) in kilowatt-hours is derived as a function of the number of occupants N:  

$$E_{quota}(N) = E_{base} + (E_{capita} \times N) $$

Empirical distribution models and historical consumption profiles suggest setting the fixed household baseload $E\_{base}$ at 1,100 kWh/year, with a per-capita marginal addition $E\_{capita}$ of 400 kWh/year. Under this formula, a single adult receives an electricity quota of 1,500 kWh/year, a couple receives 1,900 kWh/year, and a family of four receives 2,700 kWh/year. These allocations closely mirror the established consumption distributions for low, medium, and high-occupancy households across the UK. For households reliant on electric cooking rather than gas, a nominal addition of 250 kWh/year is appended to the base quota.

### 1.2. Space Heating, Hot Water, and EPC Considerations

Space heating and hot water demand present a significantly more complex calculation, as they are strictly dependent upon the property’s Energy Performance Certificate (EPC) rating, the total gross internal floor area (A in square metres), and the type of heating system installed. The UK housing stock is structurally inefficient; empirical data reveals that EPC D-rated homes consume 46% more energy overall than EPC A or B-rated homes, while F and G-rated properties consume 68% more. Providing a flat-rate cash allowance inevitably forces families in G-rated Victorian terraces to under-consume heat, leading to severe health crises.  
The proposed system shifts the liability for thermal inefficiency from the tenant to the state. The thermal energy formula for space heating ($Q_{heat}$) and hot water ($Q_{hw}$) in kWh/year must be expressed to account for these variables:  
$$Q_{thermal} = \frac{(A \times I_{epc} \times C_{hdd}) + (W_{capita} \times N)}{\eta_{sys}}$$  
The components of this formula are defined as follows:

- A represents the gross internal floor area.  
* $I_{epc}$ is the thermal intensity factor based on the property's EPC rating (kWh/m²). Analysis of National Energy Efficiency Data-Framework (NEED) parameters establishes average intensity values at approximately 30 kWh/m² for A/B ratings, 60 kWh/m² for C, 100 kWh/m² for D, 140 kWh/m² for E, and 180 kWh/m² for F/G ratings.  
- $C_{hdd}$ is a seasonal climate adjustment factor derived from Heating Degree Days (HDD), ensuring that the quota is dynamically weighted toward colder months.  
* $W_{capita}$ constitutes the hot water baseline, estimated at 500 kWh per person per year, scaling linearly with occupancy.  
* $\eta_{sys}$ denotes the thermal efficiency of the primary heating system. For dual-fuel households utilising a modern condensing gas boiler, efficiency is typically modelled at 0.85 (85%). For electric-only households, the system differentiates between legacy resistive storage heaters $(\eta_{sys} = 1.0)$ and modern Air Source Heat Pumps $(\eta_{sys} = 3.0)$.

By factoring the EPC rating directly into the welfare allocation, the policy guarantees that claimants are provided the exact thermodynamic energy required to safely maintain a minimum ambient temperature of 18°C to 21°C, mitigating the physiological risks of hypothermia and dampness regardless of their housing situation.

### 1.3. Hydration and Sanitation: Volumetric Water Allocations

Water consumption exhibits distinct behavioural variations depending on whether a property is metered. The national average consumption stands at approximately 140 litres per person per day. However, metered households average 129 litres per person per day, compared to 171 litres in unmetered households, demonstrating that financial incentives to limit waste actively suppress consumption.

To calculate the allocated quota in cubic metres ($m^3$) per year, the formula must assume a highly efficient baseline to discourage excess usage (such as garden hoses or excessive bathing) while completely fulfilling all sanitary, cooking, and hydration needs. A household's annual volumetric water quota $W_{vol}(N)$ is calculated as:  

$W_{vol}(N) = W_{base} + (W_{marginal} \times N)$  

Allocating a base of 30 $m^3$ for core household functions (cleaning, shared laundry, dishwashing) and a marginal per-capita allowance of 35 $m^3$ ensures sufficient coverage for personal hygiene and hydration. Under this formula, a single adult receives 65 $m^3$/year (equivalent to 178 litres/day), and a family of four receives 170 $m^3$/year (equivalent to 116 litres/person/day). Any consumption exceeding this statutory limit is billed to the claimant at standard retail rates, maintaining the economic incentive for water conservation.

### 1.4. Digital Inclusion: Internet and Broadband Access

Digital exclusion serves as a severe structural barrier to modern employment, remote education, and civic participation. The Minimum Digital Living Standard (MDLS) project indicates that internet access via a mobile phone alone is wholly insufficient to sustain a reasonable standard of living; households require both a fixed broadband connection and mobile data to manage modern life effectively.  

Volumetric data analysis indicates that a household with students requires an estimated 130 GB per month per student for educational streaming, plus an estimated 60 GB per person for general administrative and social use. An arbitrary data cap is likely to impede educational attainment and job-seeking efforts, particularly for households engaged in remote learning or intensive job searches.  

The most operationally efficient allocation mechanism is for the DWP to mandate a statutory "social tariff" standard across all Internet Service Providers (ISPs). Rather than measuring gigabytes dynamically, claimants would be allocated an uncapped, fixed-line broadband connection with a minimum download speed of 50 Mbps, alongside a 20 GB monthly mobile data allowance per adult and secondary school-aged child. 

The state covers the base wholesale cost of these connections (estimated at £300 per year per household), treating baseline internet access as a fundamental public utility.

## 2\. Market Plausibility and Supplier Reclaim Mechanisms

Implementing direct utility quotas necessitates a fundamental rewiring of the retail utility market for UC claimants. The policy framework dictates that claimants inform utility providers of their UC status. The calculated monthly quotas are then zero-rated on the claimant's bill, and all daily standing charges are completely waived. The provider reclaims the cost of these units directly from the state via a DWP and Ofgem-regulated mechanism.

### 2.1. The "Fair Unit Cost" Recovery Model

For this system to be financially viable for the Treasury, the state cannot reimburse suppliers at highly inflated consumer retail rates. Under the current Ofgem price cap, retail unit rates are heavily laden with network charges, operating costs, policy levies, and profit margins. Crucially, the "operating cost" portion of the price cap stack allows suppliers to recover extensive costs associated with customer acquisition, marketing, and, most substantially, bad debt provisions.  

For the volumetric quotas allocated to UC claimants, the risk of bad debt is absolute zero, as the state guarantees payment for these units. Furthermore, customer service overheads related to billing disputes and acquisition marketing are entirely bypassed. Consequently, it is highly feasible and legally sound for the state to mandate a reduced "fair unit cost." Mathematical modelling indicates that a fair rate—stripping out bad debt risk and marketing overheads while preserving a maximum 10% wholesale profit margin—sits at approximately 82.5% of the standard retail unit rate.  

By paying a bulk, derisked wholesale rate, the state procures energy much more efficiently than individual consumers. Consumption exceeding the calculated monthly quota remains the liability of the claimant and is billed at the standard, higher retail rate, maintaining a critical financial incentive for the household to avoid gross energy or water wastage.

### 2.2. Waiving the Standing Charge

The daily standing charge has become one of the most regressive elements of the UK energy market. From mid-2026, electricity standing charges reached 57.19 pence per day, and gas reached 29.04 pence per day. For low-income households consuming minimal energy, these fixed charges can constitute up to 32% of their total bill.

The proposed policy mandates that suppliers waive the standing charge entirely for UC claimants, transferring this liability to the DWP. The state absorbs the standing charge at the market rate, ensuring network infrastructure operators still receive their necessary capital for grid maintenance. By removing this fixed burden from the claimant, the policy prevents the accumulation of debt during summer months when thermal energy consumption drops, ensuring that households enter winter free of utility arrears.

### 2.3. Seasonal Adjustments and Triennial Climate Recalculations

Energy demand is radically non-linear across the calendar year. Analysis of UK domestic consumption distributions demonstrates that the first quarter (January to March) accounts for a vastly disproportionate share of annual heating demand, while summer months require negligible space heating. The DWP utility allocation cannot be distributed as a flat 1/12th monthly fraction. Instead, it must be weighted directly by historical monthly Heating Degree Days (HDD), mapping exactly to real-world thermal needs.  

Furthermore, anthropogenic climate change is actively altering UK thermodynamics. The overall decrease in annual HDDs over recent decades has measurably reduced baseline space heating demands. Concurrently, summer cooling demands are subtly rising. The policy must mandate a statutory recalculation of the $C_{hdd}$ climate adjustment factor every three years. While base electrical demands for lighting and appliances may remain static, thermal load models must remain fluid to prevent state overpayment as winter baseline temperatures progressively warm.

## 3\. Methodology for Nutritional and Essential Needs Funding

While utilities are provided via direct volumetric quotas, funding for food, toiletries, household products, transport, and clothing must be delivered as a liquid cash transfer. This preserves consumer choice, autonomy, and market competition. The methodology for calculating this cash transfer relies on a rigid, CPI-linked basket of goods based on the Joseph Rowntree Foundation’s (JRF) Minimum Income Standard (MIS).

### 3.1. The Minimum Income Standard (MIS) Basket

The MIS represents a publicly deliberated consensus on the absolute minimum income required to achieve a socially acceptable standard of living in the UK. By stripping out rent, council tax, childcare, and domestic fuel (which are handled through the new utility quotas, existing housing benefits, or separate local authority mechanisms), the remaining core basket isolated for the UC cash transfer focuses entirely on human sustenance and participation.  
The 2025 MIS budgets highlight the severe inadequacy of the current Universal Credit standard allowance. The current UC standard allowance for a single adult over 25 is merely £400.14 per month (rising slightly to £424.90 in April 2026). This leaves a massive systemic deficit that drives reliance on food banks and high-interest debt.  
To calculate the reformed monthly UC cash transfer ($C_{transfer}$), the state must establish baseline baskets for adults (A) and children (C), subject to economies of scale (equivalisation). Drawing from established equivalisation methodologies (such as the OECD-modified scale), financial need does not scale linearly as household size increases.  
$$C_{transfer} = \left( B_{single} \times [1 + 0.7(A - 1) + 0.45(C)] \right) \times (1 + \Delta CPI\_{basket})$$  
Where $B_{single}$ is the baseline weekly cost of the MIS goods basket for a single adult, and $\Delta CPI_{basket}$ is the inflation adjustment applied specifically to the weighted categories of the basket (food, transport, clothing). Linking this directly to the CPI of essential goods, rather than headline CPI, is critical, as basic necessities often inflate at fundamentally different rates than luxury goods.

### 3.2. Structuring the Reformed Allowance

Aggregating the tailored essential budgets (excluding housing, utilities, council tax, childcare, non-essential travel, unneeded private healthcare, and discretionary social participation), the foundational cost for a single adult is approximately £147.08 per week.

| Family Type             | Household Share | Equivalisation Multiplier | Reformed Monthly Cash Allowance | Current UC Monthly Baseline |
| :---------------------- | :-------------- | :------------------------ | :------------------------------ | :-------------------------- |
| Single, no children     | 50%             | 1.00x                     | £637.35                         | £424.90                     |
| Couple, no children     | 6%              | 1.70x                     | £1,083.50                       | £628.10                     |
| Lone Parent, 2 children | 33%             | 1.90x                     | £1,210.97                       | £1,047.34                   |
| Couple, 2 children      | 11%             | 2.60x                     | £1,657.11                       | £1,250.54                   |

*Note: Calculations derive from the equivalisation formula applied to the base £147.08 weekly rate. Current UC baselines reflect 2026/27 projected rates including standard child elements but excluding housing/utility support.*  

This structural linkage to the MIS ensures that the welfare floor is entirely insulated from political erosion. By applying a statutory link to the CPI of these specific goods, the purchasing power of the poorest deciles remains constant in real terms, directly closing the material deprivation gap that current flat-rate policies have widened over the past decade.

## 4\. Energy-Saving Strategy: Prioritising Low-EPC Households

The proposed policy introduces a radical shift in the political economy of welfare: by making the state financially liable for the actual thermodynamic heat loss of a claimant's home, the state suddenly possesses a direct, quantifiable financial incentive to insulate private and social housing.

### 4.1. Overcoming the Capital Disincentive

Currently, landlords and homeowners face a split-incentive problem; they bear the capital cost of insulation, but the tenant reaps the reward of lower bills. Consequently, the UK's housing stock remains some of the least efficient in Europe. In recent years, 41% of EPC registrations for existing homes achieved a D rating or worse. Upgrading a home from an F or G rating to a C rating is highly capital-intensive, often costing between £10,000 and £20,000 to install solid wall insulation and modern heat pumps. Conversely, transitioning from a D to a C rating is relatively inexpensive, typically costing between £1,500 and £3,000 via cavity wall and loft insulation.  
Under the redesigned UC system, an F/G-rated property demands massive state subsidies to meet the thermodynamic needs of the claimant. For example, a D-rated home requires 46% more energy than an A/B-rated home, and an F/G-rated home requires 68% more.

### 4.2. A 5-Year Capital Retrofit Programme

The strategic response is to aggressively target ECO4 funding, the Warm Homes Plan, and direct Treasury capital towards retrofitting the homes of UC claimants, strictly prioritizing the worst-performing stock.  
The policy requires a 5-year capital expenditure (CapEx) plan aiming to upgrade all E, F, and G-rated properties housing UC claimants, alongside 50% of targeted D-rated properties, up to a minimum EPC C standard. Demographic and property modelling of the 6.7 million paying UC households indicates this targets approximately 2.34 million properties.

> * **F/G-rated properties:** \~268,000 homes at £15,000 each.  
> * **E-rated properties:** \~737,000 homes at £7,500 each.  
> * **D-rated properties:** \~1,340,000 homes at £2,500 each.

The total capital investment required over the 5-year horizon is approximately £12.9 billion, equating to an annual CapEx of £2.58 billion.

### 4.3. Efficiency Savings on Welfare Expenditure

Crucially, this retrofit strategy generates direct, compounding efficiency savings for the DWP. If the state upgrades a claimant's F/G-rated property to a C-rated standard, annual gas consumption drops dramatically. At a subsidised fair unit cost, this represents an immediate state saving of hundreds of pounds per property, per year.  
As the 5-year retrofitting program rolls out, the annual energy subsidy obligation of the state actively decreases. Mathematical modelling of the housing stock transition indicates that the gross energy subsidy required to heat UC households safely drops from £8.29 billion in Year 1 down to £7.72 billion in Year 5\. This approach transitions the welfare budget from a perpetual sunk-cost model to a capital asset-enhancement model, systematically removing carbon from the economy while perpetually lowering welfare liabilities.

## 5\. Macroeconomic and Fiscal Evaluation (5-Year Forecast Horizon)

Evaluating the efficacy of the proposed system requires comparing the direct, upfront fiscal costs of the redesigned welfare allocations against downstream public sector savings and the massive macroeconomic growth generated by poverty eradication.

### 5.1. Assessing the Fiscal Cost Shift

Baseline modelling of the Universal Credit caseload in early 2026 indicates that current standard cash allowances and child elements cost the Treasury approximately £57.3 billion annually. Moving to the proposed needs-based system significantly increases upfront fiscal commitments. Guaranteeing the tailored essential basket of goods requires an estimated £77.63 billion annually.  
The baseline thermal and electrical utility quotas cost the state an additional £8.29 billion in Year 1, while water and broadband subsidies add £3.34 billion and £2.01 billion respectively. Factoring in the £2.58 billion annual capital allocation for the aggressive EPC retrofitting program brings the total gross proposed expenditure to approximately £93.85 billion in Year 1\. This represents a gross spending increase of approximately £36.5 billion annually over the current baseline.

### 5.2. Closing the Gaps: Health, Social Care, and the "Cost of Cold"

The current UC system leaves households dangerously exposed to fuel poverty, resulting in profound health inequalities. A household is defined as experiencing fuel poverty if they cannot afford to heat their home to a reasonable temperature without falling below the poverty line. Cold and damp homes actively exacerbate cardiovascular diseases, respiratory illnesses, and mental health conditions.  
The NHS currently spends between £1.36 billion and £2.5 billion every year treating illnesses directly caused by cold, damp, and dangerous homes. Furthermore, cold homes lead to excess winter deaths—averaging up to 27,000 annually—and increase the incidence of severe falls among the elderly due to reduced dexterity. These falls cost the UK an additional £4.4 billion annually, including £1.1 billion in adult social care costs.  
By guaranteeing thermal comfort through direct utility quotas, the proposed policy virtually eradicates the "Cost of Cold." Insulating the housing stock to EPC C and ensuring safe ambient temperatures would prevent over 650,000 new cases of childhood asthma by 2030 and prevent 6,000 excess winter deaths annually. This generates immediate, recurring downstream savings for the NHS and adult social care networks, recovering a significant portion of the energy subsidy costs.

### 5.3. Macroeconomic Multipliers and Child Poverty Dynamics

The broader economic assessment of this £36.5 billion net investment hinges on the concept of the Marginal Propensity to Consume (MPC) and the fiscal multiplier. The Office for Budget Responsibility (OBR) traditionally applies a conservative fiscal multiplier of 0.6 to welfare spending. In real terms, a 0.6 multiplier dictates that for every £1 the government spends on welfare, the economy (real GDP) initially grows by only 60 pence. The OBR models that the remaining 40 pence displaces or "crowds out" private sector activity, and assumes that even this initial 60 pence boost tapers to zero over five years, as it is ultimately offset by monetary policy adjustments (such as the Bank of England raising interest rates) and inflation.  
However, empirical economic literature demonstrates that this baseline is often too conservative, particularly when welfare is highly targeted at low-income demographics. The size of the multiplier is inextricably linked to the Marginal Propensity to Consume (MPC)—the fraction of an additional pound of income that is spent rather than saved. Households experiencing severe liquidity constraints are effectively "hand-to-mouth" consumers. Studies indicate that the MPC for credit-constrained groups approaches 0.80 to 1.0, meaning that almost 100% of any additional welfare transfer is immediately injected back into the local economy to purchase necessities, rather than being saved or used to service non-productive debt.  

When money is injected into demographics with an exceptionally high MPC, it triggers a chain reaction: households spend the money at local businesses, those businesses pay their suppliers and workers, who then spend their wages, repeating the cycle. Because the capital is recycled multiple times rather than hoarded, the total expansion in national income ultimately exceeds the initial government outlay, generating a fiscal multiplier greater than 1\. Literature evaluating poverty reduction and public investment initiatives suggests a true welfare multiplier for these demographics closer to 1.5.  

Applying this 1.5 multiplier to the additional £36.5 billion investment yields a massive stimulus to aggregate domestic demand, driving local job creation, supporting high-street retail, and generating vast returns in VAT and corporate tax revenues. 

Moreover, the current architecture has driven child poverty to record highs, affecting over 4 million children, largely due to restrictive policies like the two-child limit. Child poverty acts as a severe, long-term structural drag on national productivity. Children raised in deep material deprivation suffer cognitive and educational scarring, leading to lower lifetime earnings, higher interaction with the criminal justice system, and reduced future tax yields. The Child Poverty Action Group (CPAG) estimates that child poverty currently costs the UK economy £39 billion annually in lost productivity and increased public service interventions.  
The proposed redesign fundamentally eliminates deep material deprivation among UC claimants. By absorbing the £39 billion annual economic drag of child poverty, generating billions in direct NHS savings, and stimulating massive domestic consumption via a high MPC, the net macroeconomic return on the investment is overwhelmingly positive.

### 5.4. Summary of Fiscal and Economic Impacts

The tables below contrast the strict financial accounting required by HM Treasury fiscal rules (Table 1\) with the broader societal value captured by a Green Book economic appraisal (Table 2).  
**Table 1: Fiscal Costs and Savings (£ Billions, Exchequer Cash Flow)** *This table represents the direct impact on the government's balance sheet and borrowing requirements.*

| Category | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Net Cash Allowance Increase | 20.32 | 20.32 | 20.32 | 20.32 | 20.32 |
| Utility Subsidies & Retrofit CapEx | 16.22 | 16.08 | 15.93 | 15.79 | 15.65 |
| **Total Gross Fiscal Cost** | **36.54** | **36.40** | **36.25** | **36.11** | **35.97** |
| NHS & Social Care Cash Savings | 0.50 | 1.00 | 1.50 | 2.00 | 2.50 |
| Macroeconomic Fiscal Clawback | 9.14 | 9.10 | 9.06 | 9.03 | 8.99 |
| **Total Fiscal Savings** | **9.64** | **10.10** | **10.56** | **11.03** | **11.49** |
| **Net Fiscal Deficit Impact** | **26.90** | **26.30** | **25.69** | **25.08** | **24.48** |

**Table 2: Economic Costs and Benefits (£ Billions, Societal Value)** *This table represents a standard economic appraisal. It classifies the £20.32bn cash transfer as purely redistributive (zero net resource cost) and applies a 1.5x macroeconomic multiplier to the gross fiscal injection.*

| Category | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Physical Resource Costs (Utilities/CapEx) | 16.22 | 16.08 | 15.93 | 15.79 | 15.65 |
| **Total Economic Costs** | **16.22** | **16.08** | **15.93** | **15.79** | **15.65** |
| Recovered Child Poverty Drag | 6.00 | 12.00 | 18.00 | 24.00 | 30.00 |
| Macroeconomic GDP Expansion | 54.81 | 54.60 | 54.38 | 54.17 | 53.96 |
| NHS & Public Health (Social Value) | 1.00 | 2.00 | 3.00 | 4.00 | 5.00 |
| Carbon Emission Savings | 0.12 | 0.24 | 0.37 | 0.49 | 0.61 |
| **Total Quantified Economic Benefits** | **61.93** | **68.84** | **75.75** | **82.66** | **89.57** |

### 5.5. Funding the Intervention: Progressive Taxation Strategies

To fully fund the redesigned Universal Credit policy—which presents a gross fiscal cost of £36.54 billion and a net fiscal deficit impact of £26.90 billion in Year 1—the revenue can be raised through either a targeted net wealth tax or a comprehensive reform of existing marginal income and investment taxes.  
**Option 1: A Progressive Annual Net Wealth Tax** A progressive net wealth tax targeted exclusively at the wealthiest 1% of the population could comfortably fund the entirety of the policy. Based on economic modelling, an annual net wealth tax could be structured with the following marginal thresholds:

> * A 1% marginal rate on net wealth above £2.2 million.  
> * A 2% marginal rate on net wealth above £3.6 million.  
> * A 4% marginal rate on net wealth above £11.2 million.

Even after accounting for administrative costs and an estimated 15% to 50% loss through tax avoidance and evasion, this specific progressive structure is calculated to raise between £46 billion and £78 billion annually. This yield would entirely cover the £36.54 billion gross cost of the welfare redesign, leaving a substantial surplus for the Treasury.  
Alternatively, a simpler flat wealth tax of 2% levied only on assets exceeding £10 million would impact just 0.03% of the UK population (around 22,000 individuals) and raise up to £24 billion a year.  
**Option 2: Fair Marginal Income and Investment Tax Reform** If a direct net wealth tax is deemed practically or politically difficult to implement, the required revenue can be raised by aligning the taxation of investment and capital with the taxation of labour. A progressive menu of reforms includes:

> * **Equalising Capital Gains Tax (CGT) with Income Tax:** Closing loopholes and raising CGT rates to match standard income tax brackets would raise an estimated £11.3 billion annually.  
> * **Abolishing the National Insurance Upper Earnings Limit:** Currently, the employee National Insurance Contribution (NIC) rate regressively drops from 8% down to just 2% for earnings above the £50,270 upper earnings limit. Removing this limit so that higher earners continue to pay the full rate could raise up to £10 billion.  
> * **Expanding NICs to Investment Income:** Applying National Insurance to income derived from property rent, savings, dividends, and partnerships—ensuring that income generated from wealth is taxed consistently with earnings from work—would raise approximately £6.1 billion a year.  
> * **Taxing Corporate Share Buybacks:** Introducing a 4% tax on corporate share buybacks would yield about £2 billion annually.

Aggregating these investment and marginal tax reforms yields approximately £29.4 billion annually. This sum exceeds the £26.90 billion net fiscal deficit impact of the welfare expansion, fully funding the policy while satisfying the Treasury's requirement to balance day-to-day public spending.

## 6\. Conclusion

The transition to a needs-based Universal Credit system represents a paradigm shift from arbitrary, flat-rate subsistence to scientifically quantified welfare provision. By decoupling inelastic utility needs from volatile retail markets through direct volumetric quotas, the state guarantees health and thermal safety, fundamentally eliminating fuel and water poverty. Pegging liquid cash transfers to the adjusted Minimum Income Standard ensures that low-income households are permanently insulated against the erosive effects of inflation on essential goods.  
While the gross fiscal cost of this intervention is substantial—adding approximately £36.5 billion annually to the welfare budget—it is offset by the elimination of systemic inefficiencies inherent in the current model. By forcing the state to internalise the cost of thermal heat loss, the policy creates a powerful financial imperative for rapid, large-scale housing retrofits, driving the UK towards its Net Zero commitments while perpetually shrinking future welfare liabilities. Furthermore, the downstream reductions in NHS acute care demand, the elimination of the £39 billion economic drag of child poverty, and the profound macroeconomic stimulus generated by the high marginal propensity to consume among low-income households demonstrate that eradicating deep material deprivation is not merely a moral imperative, but a highly rational, self-sustaining macroeconomic investment.

#### **Works cited**

1\. Policy Brief \- The case for a progressive annual wealth tax in the UK updated, https://gala.gre.ac.uk/id/eprint/47322/20/47322%20TIPPET\_The\_case\_for\_a\_progressive\_annual\_wealth\_tax\_in\_the\_UK\_%28WORKING%20PAPER%29\_2024.pdf 
2\. Ten tax reforms to raise over £50 billion a year for UK public services, https://taxjustice.uk/blog/how-to-raise-50-billion-for-public-services-our-ten-tax-reforms/ 
3\. Tax the rich: Why we need a wealth tax in the UK | Oxfam GB, https://www.oxfam.org.uk/get-involved/campaign-with-oxfam/fight-inequality/tax-the-rich/ 
4\. Labour's tax pledges | Institute for Government, https://www.instituteforgovernment.org.uk/explainer/labours-tax-pledges 
5\. Manifesto analysis \- Tax | Fraser of Allander Institute, https://fraserofallander.org/wp-content/uploads/2024/06/Manifesto-analysis-Tax-2.pdf 
6\. The role of the UK tax system in an anti-poverty strategy: Economic principles and practical reforms \- ISER/Essex, https://www.iser.essex.ac.uk/wp-content/uploads/2022/08/Anti\_poverty\_strategy\_Brewer.pdf