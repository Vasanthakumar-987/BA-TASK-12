# BA T12 â€” HR Attrition Analysis Dashboard

## Objective
Analyze the assigned HR Analytics dataset in **Tableau Public** to identify patterns in employee attrition and support data-informed employee-retention decisions. The analysis compares attrition across employee demographics, departments, business travel, and educational backgrounds.

## Live Dashboard
**[View the HR Attrition Analysis Dashboard on Tableau Public](https://public.tableau.com/views/HRATTRITIONANALYSISDASHBOARD_17914401644670/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

## Dataset and Tools
- **Dataset:** Assigned `HR_Analytics.csv` (selected columns)
- **Records:** 1,470 employees
- **Fields:** 10 (`Age`, `Attrition`, `BusinessTravel`, `DailyRate`, `Department`, `DistanceFromHome`, `Education`, `EducationField`, `EmployeeCount`, `EmployeeNumber`)
- **Data quality:** No missing values; `EmployeeNumber` is unique in the supplied dataset.
- **Tool:** Tableau Public
- **Primary metric:** Employee attrition rate = employees with `Attrition = "Yes"` / total employees Ã— 100

## Dashboard Analysis and Visualizations
The analysis was developed around the following views:

| Visualization | Chart type | Purpose |
|---|---|---|
| Overall Employee Attrition | Pie / donut chart | Compare employees who left with those who remained. |
| Attrition Rate by Department | Horizontal bar chart | Identify departments with higher attrition rates. |
| Attrition Rate by Age Group | Line chart | Compare employee attrition across age brackets. |
| Attrition by Department and Business Travel | Heat map / highlight table | Examine how travel frequency and department relate to attrition. |
| Attrition by Education Field | Treemap | Compare the size of employee groups and their attrition rates. |

### Interactive Exploration
The planned dashboard filters are **Department**, **Business Travel**, and **Education Field**. Applying a filter across worksheets allows users to compare the charts for selected employee segments. Chart-level **Use as Filter** interactions can support further exploration.

### Calculated Fields
**Attrition Flag**
```tableau
IF [Attrition] = "Yes" THEN 1
ELSE 0
END
```

**Attrition Rate**
```tableau
SUM([Attrition Flag]) / COUNT([EmployeeNumber])
```
Format as a percentage in Tableau.

**Age Group**
```tableau
IF [Age] <= 24 THEN "18â€“24"
ELSEIF [Age] <= 34 THEN "25â€“34"
ELSEIF [Age] <= 44 THEN "35â€“44"
ELSEIF [Age] <= 54 THEN "45â€“54"
ELSE "55+"
END
```

## Key Findings
1. **Overall attrition:** Of **1,470 employees**, **237 left** and **1,233 stayed**, resulting in an attrition rate of **16.12%**.
2. **Age-group disparity:** Employees aged **18â€“24** have the highest attrition rate (**39.18%**, 38 of 97). The 25â€“34 group has a **20.22%** rate (112 of 554), compared with approximately 10% for ages 35â€“54.
3. **Departmental differences:** **Sales** has the highest department-level attrition rate (**20.63%**, 92 of 446), followed by **Human Resources** (**19.05%**) and **Research & Development** (**13.84%**).
4. **Business-travel association:** Employees who **travel frequently** have **24.91%** attrition (69 of 277), compared with **14.96%** for those who travel rarely and **8.00%** for employees who do not travel.
5. **Education-field differences:** Employees with a **Technical Degree** (**24.24%**) or **Marketing** background (**22.01%**) have relatively high attrition. The **Human Resources** education-field category reaches **25.93%**, but contains only 27 employees.

## Suggestions and Recommendations
1. **Strengthen early-career retention:** Review onboarding, mentoring, career progression, and support for employees under 35; investigate exit-interview reasons before selecting interventions.
2. **Review Sales department conditions:** Examine workload, performance expectations, management support, and advancement opportunities because Sales has the highest departmental attrition rate.
3. **Assess travel-related employee experience:** Survey frequent travelers and consider more predictable travel schedules, rotation of assignments, and appropriate support where practical.
4. **Investigate commuting challenges:** The attrition rate is **22.06%** for employees living **21â€“29 km** from work versus **13.77%** for those living **1â€“5 km** away. Consider testing flexible schedules or commuting support, subject to operational needs.

## Overall Conclusion
Employee attrition is unevenly distributed across the workforce. The dataset highlights higher attrition among **younger employees**, **frequent business travelers**, and **Sales employees**, suggesting that a targeted retention strategy may be more useful than one uniform policy. These are **descriptive associations, not proof of causation**; HR teams should verify underlying reasons through employee feedback and further analysis before implementing changes.

## Limitations
- The assigned subset has **no date field**, so this dashboard cannot establish a timeline or trend of attrition over multiple periods.
- Some subgroups are small; their percentages should be interpreted with caution.
- Observational comparisons do not identify the causes of employee departures.

---
**Assignment:** Business Analytics â€” Task 12 (BA T12)  
**Platform:** Tableau Public  
**Dashboard:** [HR Attrition Analysis Dashboard](https://public.tableau.com/views/HRATTRITIONANALYSISDASHBOARD_17914401644670/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
