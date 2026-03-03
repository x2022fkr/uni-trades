# Wrangling.md
## BSAD 482 – Term Project Milestone 2
**Topic:** Should priority be given to encouraging students toward university programs or skilled trades/apprenticeships given current employment outcomes, earnings potential, and student debt levels?

---

## Dataset 1: Average Loan Balance at Time of Leaving School by Study Level and Institution Type
**Source:** Employment and Social Development Canada – Canada Student Financial Assistance Program  
**File:** `07-v-avlbal-pro-eng.csv`

### Issues Encountered
- Column A contained truncated category labels that were not fully visible at default column width.
- The dataset included several category breakdowns not relevant to the research question, including gender splits (Gender-Female, Gender-Male) and institution type rows (Institution Type-Private).
- The category names were long and inconsistent (e.g., "Study Level-Certificate or Diploma"), making them difficult to use directly in visualizations.

### How Issues Were Addressed
- Column A was widened by double-clicking the column border to reveal full category names.
- Rows not relevant to the university vs. trades comparison were deleted, retaining only: Average Loan Balance-Total, Study Level-Certificate or Diploma, Study Level-Undergraduate, and Institution Type-College.
- Category labels were renamed to shorter, cleaner versions: "Trades/College", "University", and "College Institution" for readability in charts.

### Assumptions and Decisions
- "Study Level-Certificate or Diploma" was treated as the closest available proxy for trades/apprenticeship graduates, as the dataset does not separately distinguish apprenticeship completers from college diploma holders.
- All dollar values were used as reported (nominal dollars), without inflation adjustment, as the visualization focuses on relative differences across credential types rather than real purchasing power over time.

---

## Dataset 2: Student Debt from All Sources, by Province of Study and Level of Study
**Source:** Statistics Canada – National Graduates Survey, Table 37-10-0036-01  
**File:** `3710003601-eng.csv`

### Issues Encountered
- The CSV contained approximately 8 rows of metadata at the top (title, frequency, table number, release date, geography) before the actual data began.
- Footnote rows and a symbol legend appeared at the bottom of the file below the last data row.
- Some cells contained Statistics Canada quality indicators ("A" for excellent, "B" for very good, "E" for use with caution) appended directly to numeric values, making the cells non-numeric.
- The data was structured with multiple sub-rows per education level (percentage with debt, average debt in dollars, percentage who repaid), requiring careful identification of the correct rows.

### How Issues Were Addressed
- All metadata rows at the top of the file were deleted, leaving the data header as row 1.
- All footnote and symbol legend rows at the bottom were deleted.
- Cells containing quality indicators (e.g., "16,700A") were cleaned by removing the letter suffix, keeping only the numeric value.
- Only the "average debt in dollars" sub-rows were retained for each education level (College, Bachelor's, Master's, Doctorate) for the most recent reference year (2020).

### Assumptions and Decisions
- The 2020 reference year was selected as the most recent available data point for cross-credential comparison.
- College-level debt was used as the proxy for trades/apprenticeship debt burden, as apprentices are not separately categorized in the National Graduates Survey.

---

## Dataset 3: Number of Canada Apprentice Loan Recipients by Province and Territory
**Source:** Employment and Social Development Canada – Canada Student Financial Assistance Program  
**File:** `45-n-cal-pt-eng.csv`

### Issues Encountered
- No significant data quality issues were present. The file was clean with a clear header row and no metadata or footnote rows.
- The dataset included all provinces and territories individually, which was more granularity than needed for a national-level trend visualization.

### How Issues Were Addressed
- No cleaning was required. The file was used as downloaded.
- Only the "Canada" row (row 2) was used for the national trend visualization, with provincial rows ignored.

### Assumptions and Decisions
- The Canada-level total was used rather than provincial breakdowns to keep the visualization focused on the national policy decision context.
- The sharp peak in 2015-2016 was retained in the visualization as it reflects the program's launch year and is meaningful context for interpreting subsequent trends.

---

## Dataset 4: Median Employment Income of Postsecondary Graduates, 2 and 5 Years After Graduation
**Source:** Statistics Canada – Table 37-10-0280-01  
**File:** `3710028001-eng.csv`

### Issues Encountered
- The CSV contained multiple rows of metadata at the top before the data table began, including title, frequency, table number, release date, and geography fields.
- The dataset was very large, covering all fields of study broken down by credential type, making it necessary to filter carefully to relevant rows.
- Some cells contained ".." (not available) or "x" (suppressed for confidentiality) values, particularly for smaller credential categories.
- Column A labels were truncated, requiring column widening to identify correct rows.

### How Issues Were Addressed
- Metadata rows at the top and footnote rows at the bottom were deleted.
- Only the "Total, field of study" rows were retained for each credential type (College, Career/Trades, Undergraduate, Master's), as these represent the national average across all programs.
- Cells containing ".." or "x" were left blank and excluded from visualization, as no imputation was appropriate for suppressed government data.

### Assumptions and Decisions
- The most recent available cohort year (2023 constant dollars) was used for income comparisons.
- Both the 2-year and 5-year post-graduation income figures were retained to show income growth trajectories, which is more informative for the decision-maker than a single snapshot.
- "Career and technical education" was grouped with trades for the purposes of comparison, as it most closely represents apprenticeship and skilled trades pathways in this dataset.