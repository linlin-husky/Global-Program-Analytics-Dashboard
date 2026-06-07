# Global Program Analytics Dashboard

## Project Overview

This project analyzes global program participation, academic alignment, student satisfaction, and program effectiveness for university-level global experience programs.

The goal is to simulate the type of data analytics work performed by an academic planning or global programs office. Using publicly available program information from Northeastern University’s Global Experience Office website and synthetically generated student application and survey data, this project transforms raw datasets into actionable insights through Python analysis, SQL queries, predictive modeling, and interactive Tableau dashboards.

This project is designed to support data-informed decision-making around global program offerings, student experience, academic fit, and future program demand.

## Business Problem

University global programs involve multiple stakeholders, including students, faculty, academic advisors, program managers, and leadership teams. To improve program planning and student outcomes, decision-makers need to understand:

* Which global programs attract the highest student demand
* Which regions and program types have stronger enrollment trends
* How student satisfaction varies by program type, location, and academic area
* Whether programs align well with students’ academic goals
* Which programs may need improvement in advising, housing support, or academic fit
* How future application volume may change across terms

This project builds an analytics workflow to answer these questions using structured data, survey feedback, and visualization tools.

## Dataset

This project uses a hybrid dataset.

Publicly available program metadata was collected from Northeastern University’s Global Experience Office website:

https://geo.northeastern.edu/

The public program data includes information such as:

* Program name
* Program type
* Country and city
* Academic area or field of study
* Term availability
* Program description
* Course or program category

Because internal student records, application data, enrollment outcomes, course evaluations, and survey feedback are not publicly available, synthetic datasets were generated for analytics demonstration purposes.

Synthetic data includes:

* Student applications
* Enrollment outcomes
* Program capacity
* Student satisfaction scores
* Academic fit ratings
* Advisor support ratings
* Housing support ratings
* Recommendation scores
* Open-ended student feedback

The synthetic data does not represent actual Northeastern student records or internal GEO performance data.

## Project Objectives

The main objectives of this project are to:

1. Build a clean and analysis-ready global program dataset
2. Integrate program metadata, student applications, and survey feedback
3. Analyze student participation trends across regions, terms, and program types
4. Evaluate program effectiveness using enrollment, satisfaction, and completion metrics
5. Identify unmet student needs through survey feedback analysis
6. Apply predictive modeling to forecast student demand
7. Develop interactive dashboards for academic planning and stakeholder decision-making

## Tools and Technologies

* Python
* Pandas
* NumPy
* scikit-learn
* SQL
* Tableau
* Excel
* Jupyter Notebook
* GitHub

## Data Pipeline

The project follows an end-to-end analytics workflow:

1. Data Collection
   Collect public program metadata from GEO webpages and prepare synthetic application and survey datasets.

2. Data Cleaning
   Clean missing values, standardize program names, validate categorical fields, and remove duplicate records.

3. Data Integration
   Join program metadata, application records, and survey feedback into analysis-ready datasets.

4. Exploratory Data Analysis
   Analyze enrollment rates, program demand, satisfaction trends, and academic fit across different dimensions.

5. Survey Feedback Analysis
   Analyze student feedback ratings and categorize open-ended feedback into common issue areas such as advising, housing, academic fit, cost, and cultural experience.

6. Predictive Modeling
   Apply regression, clustering, and forecasting techniques to predict program demand and group programs by performance profile.

7. Dashboard Development
   Build interactive Tableau dashboards to communicate findings to both technical and non-technical stakeholders.

## Key Analyses

### 1. Program Demand Analysis

This analysis identifies which global programs receive the highest number of applications and which programs have lower enrollment rates.

Example questions:

* Which program types have the highest demand?
* Which regions attract the most student interest?
* Which programs are underfilled or over-demanded?
* How does demand change across academic terms?

### 2. Student Satisfaction Analysis

This analysis evaluates student experience based on satisfaction scores, recommendation scores, and support-related survey ratings.

Example questions:

* Which programs have the highest student satisfaction?
* Which program types receive lower support ratings?
* Is housing support associated with overall satisfaction?
* Are students more satisfied in certain regions or academic fields?

### 3. Academic Alignment Analysis

This analysis examines whether global programs align with students’ academic interests and curriculum requirements.

Example questions:

* Which academic areas are most represented in global programs?
* Which programs have strong academic fit ratings?
* Are some colleges or majors underserved by current program offerings?
* Which programs may need stronger curriculum integration?

### 4. Survey Feedback Analysis

This analysis uses structured ratings and open-ended feedback to identify recurring student needs.

Feedback categories include:

* Academic fit
* Advising support
* Housing and logistics
* Cost concerns
* Cultural experience
* Program communication
* Career relevance

### 5. Predictive Modeling

This project applies statistical and machine learning methods to support future planning.

Models include:

* Regression model to predict student satisfaction
* Clustering model to group programs by performance profile
* Forecasting model to estimate future application volume

## Dashboard Features

The Tableau dashboard includes:

* Total applications
* Total enrollments
* Enrollment rate
* Average satisfaction score
* Average academic fit score
* Program demand by region
* Program satisfaction by type
* Application trends by term
* Enrollment rate vs. satisfaction scatter plot
* Program performance ranking
* Filters for region, term, academic area, and program type

## Example Insights

Sample insights generated from the analysis may include:

* Dialogue-style programs show strong student satisfaction but may have limited capacity.
* Programs in high-demand regions may require expanded offerings or additional sections.
* Housing support and advising support are strongly associated with overall satisfaction.
* Some academic fields have fewer global program options, suggesting opportunities for future program development.
* Programs with high academic fit and high satisfaction can serve as models for future program design.

## Repository Structure

```text
global-program-analytics-dashboard/
│
├── data/
│   ├── raw/
│   │   ├── geo_programs_raw.csv
│   │   ├── applications_raw.csv
│   │   └── survey_feedback_raw.csv
│   │
│   ├── processed/
│   │   ├── programs_cleaned.csv
│   │   ├── applications_cleaned.csv
│   │   ├── survey_feedback_cleaned.csv
│   │   └── final_analysis_dataset.csv
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   ├── 03_survey_feedback_analysis.ipynb
│   └── 04_predictive_modeling.ipynb
│
├── sql/
│   ├── create_tables.sql
│   ├── data_quality_checks.sql
│   └── analysis_queries.sql
│
├── tableau/
│   └── global_program_dashboard.twbx
│
├── reports/
│   └── executive_summary.md
│
├── scripts/
│   ├── generate_synthetic_data.py
│   ├── clean_data.py
│   └── export_dashboard_data.py
│
└── README.md
```

## Database Design

The SQL database includes the following tables:

### programs

Stores program-level information.

Key fields:

* program_id
* program_name
* program_type
* country
* city
* region
* academic_area
* term

### applications

Stores student application and enrollment records.

Key fields:

* application_id
* student_id
* program_id
* application_term
* application_status
* enrolled
* completion_status

### survey_feedback

Stores student survey responses.

Key fields:

* response_id
* student_id
* program_id
* satisfaction_score
* academic_fit_score
* advisor_support_score
* housing_support_score
* recommend_score
* feedback_text

### courses

Stores course and academic alignment information.

Key fields:

* course_id
* program_id
* course_title
* academic_area
* credit_type
* nupath_attribute

## Data Quality Checks

Data quality checks include:

* Missing value detection
* Duplicate record detection
* Invalid program IDs
* Invalid satisfaction score ranges
* Inconsistent program type labels
* Application records without matching program records
* Survey responses without matching student or program records

## Predictive Modeling

The project includes the following modeling tasks:

### Satisfaction Prediction

A regression model is used to predict overall student satisfaction based on academic fit, advising support, housing support, program type, and region.

### Program Performance Clustering

A clustering model groups programs into performance categories based on enrollment rate, satisfaction score, completion rate, and recommendation score.

### Demand Forecasting

A forecasting model estimates future application volume by term, region, and program type.

## Tableau Dashboard

The Tableau dashboard is designed for academic planning stakeholders.

Dashboard pages include:

1. Executive Overview
2. Program Demand Analysis
3. Student Satisfaction Analysis
4. Academic Alignment Analysis
5. Survey Feedback Insights
6. Predictive Planning

## Limitations

This project uses synthetic student-level data for demonstration purposes. The results should not be interpreted as actual Northeastern University program performance or student outcomes.

The purpose of this project is to demonstrate an end-to-end analytics workflow, including data cleaning, integration, visualization, automation, and predictive analysis in a higher education global programs context.

## Future Improvements

Future improvements may include:

* Connecting the pipeline to live survey tools such as Qualtrics or Google Forms
* Automating dashboard refreshes
* Adding API-based data ingestion
* Applying natural language processing to open-ended feedback
* Building a recommendation system for matching students with global programs
* Expanding analysis to include cost, scholarships, and career outcomes

## Skills Demonstrated

This project demonstrates:

* Data cleaning and validation
* Exploratory data analysis
* SQL database design and querying
* Survey feedback analysis
* Predictive modeling
* Tableau dashboard development
* Data automation
* Higher education analytics
* Cross-functional stakeholder communication
* Actionable insight generation

## Resume Summary

Global Program Analytics Dashboard | Python, SQL, Tableau, Excel, scikit-learn

* Built an end-to-end analytics project using public global program metadata and synthetic student application and survey data to evaluate program demand, academic alignment, and student satisfaction.
* Cleaned, validated, and integrated multi-source datasets with Python and SQL, creating analysis-ready tables for participation trends, survey feedback, and program performance metrics.
* Developed interactive Tableau dashboards to visualize enrollment rates, regional demand, program satisfaction, and academic fit for stakeholder decision-making.
* Applied regression, clustering, and forecasting techniques to identify high-performing programs, predict student demand, and recommend strategies for improving global program offerings.
