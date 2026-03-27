# Pathways to Prosperity: University or Skilled Trades?

## Decision Statement

**Should a Nova Scotia high school guidance counselor prioritize encouraging students toward university programs or skilled trades/apprenticeships given current employment outcomes, earnings potential, and student debt levels?**

---

## Executive Summary

Nova Scotia high school guidance counselors face a consequential decision every time they advise a graduating student: recommend university, or recommend skilled trades? For decades, the default has been university — reinforced by parental expectations, social prestige, and institutional incentives. But labour market data increasingly suggests this default may be failing many students.

The province needs 11,000 new tradespeople by 2030, labour shortages cost Nova Scotia businesses approximately $1 billion in 2022, and 35% of current trades workers are over 55 and approaching retirement. Meanwhile, the average Canadian university graduate carries $28,000–$29,000 in student debt, taking 10 years to repay. This project uses Statistics Canada data on student loan balances, graduate incomes, and debt levels to analyze the financial tradeoffs between these two pathways and provide evidence-based guidance for counselors.

The analysis reveals that university loan balances are growing faster than trades loan balances ($227/year vs. $154/year), that trades graduates carry proportionally less debt relative to their early income (37.7% vs. 52.1%), and that trades graduates accumulate more total wealth than university graduates for approximately 13 years after high school. University does produce higher long-term earnings, but the advantage takes far longer to materialize than most people assume. The recommendation is not "trades over university" but rather a student-profile-based approach that matches each student's financial situation, aptitudes, and career goals to the pathway most likely to serve them well.

---

## Table of Contents

1. [Background](#background)
2. [Data Sources](#data-sources)
3. [Exploratory Findings](#exploratory-findings)
4. [System Dynamics](#system-dynamics)
5. [Analysis](#analysis)
6. [Recommendations](#recommendations)
7. [Limitations & Future Work](#limitations--future-work)
8. [References](#references)
9. [Reflection](#reflection)

---

## Background

For detailed background on this decision, see [Background.md](Background.md).

High school guidance counselors in Nova Scotia occupy a pivotal position in shaping the province's future workforce and their students' financial trajectories. Nova Scotia faces a critical skilled trades shortage, with the province needing 11,000 new tradespeople by 2030 to meet construction and infrastructure demands (Government of Nova Scotia, 2023). This labour gap is already causing significant economic damage — in 2022 alone, Nova Scotia businesses missed out on approximately $1 billion worth of potential sales and contracts due to insufficient skilled workers (Gorman, 2023).

Meanwhile, university graduates face a different but equally serious challenge: student debt. The average Canadian university graduate carries between $28,000 and $29,000 in student-related debt, taking an average of 10 years to repay (Debt.ca, 2025). More than half of bachelor's degree recipients graduate with debt, and this financial burden significantly impacts young adults' ability to purchase homes, start families, or take entrepreneurial risks.

The tension counselors face stems from decades of cultural emphasis on university as the default pathway to success. As Duncan Williams, president and CEO of the Construction Association of Nova Scotia, has noted, the education system has largely focused on promoting university even though it is not the best option for every student (Canadian Broadcasting Corporation, 2022). The province has recognized this imbalance and invested $100 million over three years to accelerate skilled trades growth, including the MOST tax rebate program for workers under 30 in eligible trades (Government of Nova Scotia, 2023).

---

## Data Sources

All datasets are stored in the [`data/`](data/) folder. For detailed wrangling documentation, see [Wrangling.md](Wrangling.md).

| Dataset | Source | Description |
|---------|--------|-------------|
| `07-v-avlbal-pro-eng.csv` | ESDC, 2009–2022 | Average federal student loan balance at time of leaving school, by study level |
| `3710028001-eng.csv` | Statistics Canada | Median employment income 2 and 5 years after graduation, by credential type |
| `45-n-cal-pt-eng.csv` | Statistics Canada, 2020 | Average student debt at graduation by credential level |

**Data Citations:**

- Employment and Social Development Canada. (2024). *Student financial assistance data for the Canada Student Financial Assistance Program* [Data set]. Open Government Portal. https://open.canada.ca/data/en/dataset/0840231b-5bbf-447f-81ce-3ec0673aefc4
- Statistics Canada. (2025). *Characteristics and median employment income of longitudinal cohorts of postsecondary graduates two and five years after graduation* [Table 37-10-0280-01]. https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3710028001

---

## Exploratory Findings

### Figure 1: Average Student Loan Balance at Graduation — Trades vs. University (2009–2022)

![Figure 1](img/viz1.png)

University graduates have consistently carried significantly higher debt loads than trades/college graduates over the entire 13-year period. Starting at approximately $15,800 in 2009–2010, university loan balances rose to $18,000 by 2021–2022. Trades/college graduates averaged around $9,400 at the start and $12,200 by the end — roughly 35% less debt at graduation. The gap widened in the final years, suggesting the debt divergence between pathways is accelerating.

### Figure 2: Median Employment Income 2 and 5 Years After Graduation by Credential Type

![Figure 4](img/viz4.png)

Career and trades graduates earned $44,300 at 2 years and $52,700 at 5 years after graduation — notably higher than college certificate holders and competitive with bachelor's degree holders ($58,700 at 2 years, $70,800 at 5 years). When debt load is factored in, trades graduates reach positive net financial position much earlier than university graduates.

### Figure 3: Canada Apprentice Loan Recipients Over Time (2014–2022)

![Figure 3](img/viz3.png)

After a strong launch in 2015–2016 with 16,422 recipients nationally, the number of apprentices accessing the Canada Apprentice Loan declined steadily, falling to just 8,000 in 2020–2021. This suggests that awareness of trades financing options is low — students may be choosing university not because it is the better path, but because they are unaware that interest-free apprenticeship loans exist.

---

## System Dynamics

### Final Causal Loop Diagram

![Final CLD](img/cld-final.png)

### CLD Explanation

The causal loop diagram identifies three feedback loops that shape how students are channeled into university or trades pathways, and it reveals why the current system is stuck in a pattern that overproduces university graduates while starving the trades pipeline.

**R1 — University Prestige Reinforcing Loop.** This is the dominant loop driving the current system. High social prestige associated with university education drives parental expectations that their children will attend university. These expectations increase university enrollment, which further reinforces university's position as the default pathway and sustains its cultural prestige. This self-reinforcing cycle explains why university enrollment has continued growing even as graduate employment outcomes have softened and debt levels have risen. The loop is deeply embedded in Nova Scotia's culture and institutional structures, making it resistant to change through information alone.

**B1 — Debt Stress Balancing Loop.** As university enrollment grows, aggregate student debt levels rise. Higher debt produces graduate financial stress, which over time reduces the perceived attractiveness of university as a pathway. This balancing loop acts as a natural brake on R1 — but it operates slowly, since the consequences of debt are felt years after the enrollment decision is made. The data in our analysis shows this loop may be beginning to exert pressure: university loan balances are growing at $227 per year and the debt-to-income ratio for bachelor's graduates (52.1%) is the highest of any credential type. However, because the feedback is delayed, students making decisions today do not yet feel the full weight of this loop.

**R2 — Trades Wage Reinforcing Loop.** In the trades pathway, enrollment feeds into the skilled trades worker supply. With Nova Scotia's construction and infrastructure demand high and rising, constrained supply pushes wages upward, which in turn makes trades careers more attractive and draws more enrollment. This is a virtuous cycle that could help address the province's 11,000-worker shortage — but only if the counselor intervenes to direct more students into the loop. Currently, R2 is weak because R1 dominates the system. The counselor is the critical leverage point because they sit at the junction where students are channeled into either R1 or R2.

**Leverage Point: The Guidance Counselor.** The counselor's recommendation directly influences both university enrollment and trades enrollment. By providing students and parents with evidence-based financial comparisons — including debt trajectories, debt-to-income ratios, and cumulative earnings projections — the counselor can weaken the grip of R1 and activate R2. This is a high-leverage, low-cost intervention: it does not require policy changes, new funding, or institutional reform. It requires only that counselors have access to current data and the confidence to present trades as a financially sound choice for the right students.

---

## Analysis

For the full Milestone 3 analysis, see [Analysis.md](Analysis.md).

### Method: Time Series Analysis (Path B3)

A Holt's Double Exponential Smoothing model was applied to 13 years of student loan balance data (2009–2022) to forecast debt trajectories for both pathways through 2027. The model was validated on held-out data (2021–2022) and supplemented with a cumulative net earnings model integrating debt and income data.

### Key Results

**Debt Forecast:** University loan balances are projected to reach ~$20,800 by 2027 compared to ~$13,500 for trades/college — a gap exceeding $7,300.

![Forecast](img/fig2_forecast.png)

**Cumulative Earnings:** Trades graduates maintain a cumulative wealth advantage for approximately 13 years after high school graduation. Bachelor's degrees do not overtake trades in total accumulated earnings until roughly age 32.

![Cumulative Earnings](img/fig4_cumulative_earnings.png)

**Debt-to-Income Ratio:** Bachelor's graduates carry debt equal to 52.1% of their early post-graduation income, compared to 37.7% for trades graduates.

![Debt to Income](img/fig5_debt_income_ratio.png)

**Model Accuracy:** The university model achieved a MAPE of 0.41% on validation data; the trades model achieved 6.05% MAPE. Both are within acceptable ranges for this type of forecasting.

All analysis code is in [`src/analysis.py`](src/analysis.py).

---

## Recommendations

Based on the analysis conducted in this project, my recommendation to Nova Scotia high school guidance counselors is to **adopt a pathway-matching framework** rather than defaulting to university for all academically capable students. The evidence does not support a blanket recommendation of trades over university or vice versa. Instead, it supports a differentiated approach that matches each student's financial circumstances, aptitudes, and career goals to the pathway most likely to produce strong outcomes.

The data makes three things clear. First, the financial burden of university is substantial and growing. University loan balances have increased at roughly $227 per year over the past 13 years and are projected to exceed $20,000 by 2027. Bachelor's degree holders carry debt equal to 52.1% of their early post-graduation income — the highest ratio of any credential type. For students from low-income backgrounds or those who are debt-averse, this burden represents a significant risk, particularly if they enter fields with weaker employment prospects. Second, trades careers are not a financial sacrifice. Trades graduates earn $44,300 within two years of graduation, accumulate more total wealth than university graduates for approximately 13 years, and carry far less debt. For students with hands-on aptitudes and an interest in construction, mechanical, or technical careers, trades offer earlier financial independence with competitive long-term earnings. Third, university remains the stronger choice for students pursuing careers that require a degree — healthcare, education, engineering, technology, and the sciences. The long-term earnings premium for bachelor's degree holders is real, even if it takes 14 years to materialize in cumulative terms.

Counselors should consider several concrete next steps. They should present students and parents with side-by-side financial comparisons of both pathways, including debt projections, early income benchmarks, and cumulative earnings timelines. They should actively inform students about trades financing options such as the Canada Apprentice Loan, since declining uptake suggests low awareness. They should also connect students considering trades with the MOST tax rebate program, which returns provincial income tax on the first $50,000 of income for eligible workers under 30.

Key uncertainties remain. The analysis uses national-level data, and Nova Scotia-specific outcomes may differ. Income figures represent medians across all fields, while individual outcomes vary enormously by specialization. Policy changes — such as expanded loan forgiveness or shifts in apprenticeship funding — could alter the financial calculus significantly. Additional data on Nova Scotia-specific graduate outcomes, field-level earnings breakdowns, and long-term career satisfaction would strengthen this analysis considerably.

---

## Limitations & Future Work

**Data limitations:** The analysis relies on only 13 annual observations for the time series forecast, uses national rather than Nova Scotia-specific data, reports nominal rather than inflation-adjusted dollars, and groups apprenticeship completers with college diploma holders due to data availability constraints.

**Methodological limitations:** The cumulative earnings model uses simplified assumptions about income growth, debt repayment, and part-time earnings during school. The exponential smoothing forecast cannot account for potential policy changes or economic shocks.

**Future work:** A stronger version of this analysis would incorporate Nova Scotia-specific graduate outcomes from the NS Labour Market Information Portal, field-of-study-level income breakdowns, career satisfaction survey data, and a longer time series to support more robust forecasting methods such as ARIMA.

---

## References

Canadian Broadcasting Corporation. (2022, June 12). Nova Scotia in midst of labour shortage in skilled trades, experts say. *CBC News*. https://www.cbc.ca/news/canada/nova-scotia/nova-scotia-skilled-trades-shortage-1.6484170

Debt.ca. (2025, June 25). The state of student debt in Canada. https://www.debt.ca/blog/the-state-of-student-debt-in-canada

Employment and Social Development Canada. (2024). *Student financial assistance data for the Canada Student Financial Assistance Program* [Data set]. Open Government Portal. https://open.canada.ca/data/en/dataset/0840231b-5bbf-447f-81ce-3ec0673aefc4

Gorman, M. (2023, November 28). Labour shortages cost N.S. businesses $1B in missed opportunities in 2022, report says. *CBC News*. https://www.cbc.ca/news/canada/nova-scotia/labour-shortages-business-workers-jobs-1.7042721

Government of Nova Scotia. (2023, October 19). Actions to accelerate skilled trades growth [Press release]. https://news.novascotia.ca/en/2023/10/19/actions-accelerate-skilled-trades-growth

Grillo de Lambarri, G. (2025, May 24). N.S. needs far more tradespeople. Diversity is key to meeting that demand, expert says. *CBC News*. https://www.cbc.ca/news/canada/nova-scotia/trades-workers-diversity-jobs-expert-1.7529090

Statistics Canada. (2020, November 17). Labour market outcomes of postsecondary graduates, class of 2015. https://www150.statcan.gc.ca/n1/pub/81-595-m/81-595-m2020002-eng.htm

Statistics Canada. (2025). *Characteristics and median employment income of longitudinal cohorts of postsecondary graduates two and five years after graduation* [Table 37-10-0280-01]. https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3710028001

---

## Reflection

This project changed how I think about the university-versus-trades question. Before starting, I held the common assumption that university was the financially superior choice for most students. The data told a more nuanced story: trades graduates reach financial stability years earlier, carry significantly less debt, and earn competitive incomes — while university's earnings premium takes over a decade to materialize in cumulative terms.

The most valuable skill I developed was connecting quantitative analysis to a real decision. Building a forecast model is one thing; translating its outputs into actionable advice for a guidance counselor is another. I also gained a deeper appreciation for the limitations of aggregate data — national medians mask enormous variation by field, region, and individual circumstance.

If I were to do this project again, I would invest more time sourcing Nova Scotia-specific data and would attempt to build field-of-study-level comparisons rather than relying on credential-level averages. I would also explore building the interactive dashboard (Path C) to let counselors explore the data themselves.
