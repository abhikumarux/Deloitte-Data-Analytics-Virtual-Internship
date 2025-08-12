
# Deloitte Data Analytics (Forage)

This repo documents my work for the **Deloitte Data Analytics Virtual Internship** (Forage). I completed **two tasks** focused on telemetry analysis (Tableau) and pay-equity classification (Excel). Each section includes background context, the specific question or goal, my interpretation, what I built, and the files involved.

----------

## 🧭 Contents


- [Task 1 — Data Analysis (Telemetry)](#task-1--data-analysis-telemetry)
  
- [Task 2 — Forensic Technology (Pay Equity)](#task-2--forensic-technology-pay-equity)

- [Key Takeaways](#key-takeaways)
  
- [How to Reproduce](#how-to-reproduce)
  
- [Notes & Reflections](#notes--reflections)


----------

## Task 1 — Data Analysis (Telemetry)

**Background**  
Daikibo Industrials operates four factories (Tokyo, Osaka, Berlin, Shenzhen), each with nine machine types sending telemetry every 10 minutes. The client unified one month of data (May 2021) into a single JSON file. They wanted to know:

1.  In which location did machines break the most?
    
2.  Which machines broke most often in that location?
    

**My Interpretation & Goal**  
Transform raw telemetry into clear insights using Tableau, highlighting the factory with the most downtime and identifying the worst-performing device type there.

**What I Did**

-   Created a calculated field: `IF [Status] = "unhealthy" THEN 10 ELSE 0 END` (10 minutes per unhealthy reading).
    
-   Built:
    
    -   Bar chart: Downtime per Factory.
        
    -   Bar chart: Downtime per Device Type.
        
    -   Linked charts with a filter to drill down from factory to devices.
        

**Result**

-   Identified **Seiko** as the highest-downtime factory.
    
-   Isolated one device type as the main cause of downtime.    

----------

## Task 2 — Forensic Technology (Pay Equity)

**Background**  
Following complaints about salary inequality, the Forensic Tech team quantified gender pay equality for job roles across all locations (scores from –100 to +100, with 0 as ideal). My task was to finish the classification.

-   Fair (+-10)
-   Unfair (<-10 AND >10)
-   Highly Discriminative (<-20 AND >20)

**My Interpretation & Goal**  
Group roles into Fair, Unfair, or Highly Discriminative based on the magnitude of bias, ignoring direction.

**What I Did**

-   Created a new column **Equality class** in Excel.
    
-   Applied formula:
    

```
=IFS(
  C2="", "",
  ABS(C2)<=10, "Fair",
  ABS(C2)<=20, "Unfair",
  TRUE, "Highly Discriminative"
)
```

-   Used `ABS()` to classify by distance from zero.
    

**Result**

-   Each role labeled by severity of inequality.
    
-   Clear separation between low, moderate, and severe bias.

----------

## Key Takeaways

-   Translate business questions into data fields and logic.
    
-   Use interactivity for deeper exploration.
    
-   Separate direction and magnitude when analyzing bias.
    
-   Keep classification thresholds explicit and documented.
    
-   Completed a Deloitte Australia Data Analytics Job Simulation on Forage (Aug 2025):
    
    -   Created a data dashboard using Tableau.
        
    -   Used Excel to classify data and draw business conclusions.
        
    -   Strengthened real-world data analysis skills in a client context.
        

----------

## How to Reproduce

### Task 1 (Tableau)

1.  Import JSON.
    
2.  Create calculated field `Unhealthy`.
    
3.  Build downtime bar charts by factory and device type.
    
4.  Link charts with a filter.
    

### Task 2 (Excel)

1.  Open Equality Table.
    
2.  Add **Equality class** column.
    
3.  Apply classification formula.
    
4.  Save classified table.
    

----------

## Notes & Reflections

Participating in Deloitte’s Forage program was incredibly useful to understand what it might be like to be part of a team at Deloitte. I was able to:

-   Analyse data and create a dashboard.
    
-   Practise using Tableau and Excel.
    
-   Build my data analysis skills in a real-world context.
    

Doing this program confirmed that I really enjoy working on technology problems for clients and I’m excited to apply these skills in a professional setting. It also reinforced the importance of:

-   Designing data solutions that directly answer client questions.
    
-   Communicating findings in a clear, interactive, and actionable way.
    
-   Using both technical tools and business logic to draw meaningful conclusions.
    

----------

_Built by Abhishek — Computer Science student & aspiring Data Analyst._
