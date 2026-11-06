# PharmaLens: Commercial Sales & Performance Analytics

An interactive Power BI portfolio project exploring pharmaceutical wholesale and retail sales performance, with a focus on product contribution, distributor and customer activity, geographical trends, and sales-team effectiveness.

> **Project scope:** This analysis uses pharmaceutical sales data. It is a commercial-sales analytics exercise, not an analysis of CT scanners, MRI systems, surgical equipment, or other medical devices.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Context](#business-context)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Tools and Technologies](#tools-and-technologies)
- [Analytical Workflow](#analytical-workflow)
- [Dashboard Pages](#dashboard-pages)
- [How to Explore the Project](#how-to-explore-the-project)
- [Key Analytical Dimensions](#key-analytical-dimensions)
- [Insights and Interpretation](#insights-and-interpretation)

---

## Project Overview

PharmaLens examines sales transactions from a pharmaceutical manufacturing business that serves customers through distributors. The project organizes sales information into an interactive reporting experience so that commercial stakeholders can review performance from three perspectives:

1. **Executive performance** — an at-a-glance view of sales across time, products, customer locations, and sales channels.
2. **Distributor and customer performance** — a more detailed view of sales contribution by distributor, customer, product, and geography.
3. **Sales-team performance** — a view of sales contribution by team, manager, representative, product, and product class.

The objective is to demonstrate how transactional data can be explored, prepared, modelled, and presented in Power BI to support business reporting and commercial decision-making.

## Business Context

The source project describes a pharmaceutical manufacturing company with operations across multiple markets. For the regional scenario covered by the dataset, the analysis focuses on **Germany and Poland**.

The company does not sell directly to end customers in this scenario. Instead, it works with distributors and receives distributor-level wholesale-to-retail sales information. This makes it possible to examine sales beyond the distributor relationship and understand activity at the customer and product levels.

The dataset includes customer types such as hospitals and pharmacies, along with channel sub-types such as government and private-sector buyers.

## Business Questions

The report is structured around questions relevant to executive, sales-management, and sales-leadership stakeholders.

### Executive view

- How are sales changing across years and months?
- Which customer cities contribute the most sales?
- How do sales vary by channel and sub-channel?
- Which product class and individual product contribute the most revenue?
- Which customer city is the leading contributor to sales?

### Distributor and customer view

- How is sales contribution distributed across wholesalers/distributors?
- Which products contribute most to each distributor's sales?
- Who are the leading customers and customer cities?
- How are sales split across channels and sub-channels?
- How does the product mix vary across customers and distributors?

### Sales-team view

- How do sales teams compare in overall sales contribution?
- Which managers and sales representatives contribute the most?
- How does each sales team perform across products and product classes?
- Which products account for the largest share of a team's sales?
- How does performance change when the reporting period is filtered by year or month?

## Dataset

The underlying data is described as pharmaceutical **wholesale-retail sales data** collected from distributors. The source project identifies the raw file as `pharma-data.csv` and credits Foresight BI as the dataset source.

### Fields in the source dataset

| Field | Description |
|---|---|
| `Distributor` | Name of the wholesaler or distributor |
| `Customer Name` | Name of the customer |
| `City` | Customer's city |
| `Country` | Customer's country |
| `Latitude` | Customer's geographical latitude |
| `Longitude` | Customer's geographical longitude |
| `Channel` | Buyer category, such as Hospital or Pharmacy |
| `Sub-channel` | Buyer segment, such as Government or Private |
| `Product Name` | Name of the drug/product |
| `Product Class` | Drug category or class, such as Antibiotics |
| `Quantity` | Quantity purchased |
| `Price` | Selling price recorded for the product |
| `Sales` | Sales amount recorded for the transaction |
| `Month` | Month in which the sale was made |
| `Year` | Year in which the sale was made |
| `Name of Sales Rep` | Sales representative associated with the transaction |
| `Manager` | Manager associated with the sales representative |
| `Sales Team` | Sales team associated with the representative |

**Data note:** The repository's tracked project files include the Power BI report and the exploratory notebook. The raw CSV is referenced in the source project's documentation but is not listed among those tracked files. Check the notebook for its expected input path before attempting to rerun the analysis from scratch.

## Tools and Technologies

| Tool | Role in the project |
|---|---|
| **Power BI Desktop** | Data modelling, report development, and interactive visualisation |
| **Power Query Editor** | Data preparation, column-name correction, and data-type assignment |
| **Python** | Initial dataset exploration |
| **Pandas** | Tabular profiling and exploratory data analysis |
| **Jupyter Notebook** | Documenting the exploratory analysis workflow |

## Analytical Workflow

The project follows a practical analytics workflow, from understanding the raw data to presenting business views.

### 1. Exploratory data analysis

The source notebook uses Pandas to inspect the dataset before report development. The documented checks include:

- Reviewing the dataset's dimensions and column types
- Checking for missing values
- Looking for unusual observations and potential outliers
- Checking for invalid or unexpected values, including negative values in the sales field
- Distinguishing categorical fields from numeric fields
- Reviewing the range and distribution of numeric columns

### 2. Data preparation

The source project describes the dataset as relatively clean and well organised. The documented Power Query preparation includes:

- Correcting column headings
- Assigning appropriate data types to columns

Additional cleaning or transformation steps should only be documented here after they have actually been implemented in the report.

### 3. Data modelling

The source project describes separating the original single-table data into fact and dimension tables and relating them through a **star-schema-style model**. In that model, the fact table holds transactional measures, while dimension tables provide descriptive context for analysis.

The exact table names and relationships should be verified in the supplied `.pbix` file before documenting them individually.

### 4. Report development

The prepared model is presented through three interactive Power BI report pages. The report supports time-based filtering, including year and month selections where applicable.

## Dashboard Pages

### 1. Executive Summary

A high-level view of overall sales performance. The page is intended to help an executive user review sales by time period, customer city, channel, sub-channel, product, and product class.

**Questions supported:**

- What is the overall sales performance for the selected period?
- Which products or product classes lead in sales?
- Which customer cities contribute the most?
- How does sales contribution vary by channel and sub-channel?

### 2. Distributor & Customer Analysis

A detailed view of sales from distributor and customer perspectives. The report supports drill-down from distributor-level performance to product-level contribution.

**Questions supported:**

- Which distributors contribute the most sales?
- Which products drive sales for a selected distributor?
- Which customers and cities are the leading contributors?
- How are sales distributed across channels and sub-channels?

### 3. Sales Team Performance

A detailed view of sales contribution by sales team, manager, representative, product, and product class.

**Questions supported:**

- Which sales teams contribute the most sales?
- Which managers and sales representatives are leading contributors?
- Which products and product classes drive each team's performance?
- How does the view change across selected years and months?

## How to Explore the Project

### Option 1: Open the Power BI report

1. Open the repository on GitHub.
2. Select `pharma-analysis.pbix`.
3. Download the file to your computer.
4. Open it using **Microsoft Power BI Desktop**.
5. Navigate through the report pages and interact with the available filters and visuals.

The source project's documentation states that the PBIX contains the normalized data model, so the raw CSV may not be required simply to open and inspect the saved report. Refreshing or rebuilding the data preparation workflow may require the original CSV and the correct source-file path.

### Option 2: Review the exploratory notebook

1. Open `data-exploration.ipynb` in GitHub, Jupyter Notebook, or JupyterLab.
2. Review the data-profiling steps and observations.
3. To execute the notebook, provide the input CSV at the path expected by the notebook and install the required Python packages, including Pandas.

## Key Analytical Dimensions

The report brings together several dimensions that are useful in commercial sales analysis:

| Dimension | Example analysis |
|---|---|
| Time | Sales by year and month |
| Product | Sales by product and product class |
| Customer | Sales by customer and customer city |
| Distribution | Sales by distributor |
| Channel | Hospital and pharmacy contribution |
| Sub-channel | Government and private-sector contribution |
| Sales organisation | Sales team, manager, and sales representative |
| Geography | Country, city, latitude, and longitude |

## Insights and Interpretation

The dashboard is designed to make it easier to identify leading products, customer locations, distributors, channels, and sales-team contributors. The value of these views is in helping a business user investigate **where sales are coming from**, **which products are contributing**, and **how performance differs across the sales organisation**.

Any numerical findings, rankings, or business recommendations should be reported only after validating them against the current dataset and the filters applied in Power BI. This README intentionally does not state specific revenue totals, growth rates, or performance improvements that have not been independently verified.
