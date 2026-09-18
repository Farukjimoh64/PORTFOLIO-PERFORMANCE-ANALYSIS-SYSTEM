# PORTFOLIO-PERFORMANCE-ANALYSIS-SYSTEM
The SmartInvest Africa Portfolio Performance Analysis System is a python-based portfolio analytics project developed by Team-D as part of a practical Python Study Group Project. The system takes a fictitious investment  portfolio stored as a list of dictionaries and transforms raw investment records into structured portfolio insights  

# SmartInvest Africa — Portfolio Performance Analysis System
(From Raw Investment Data to Actionable Portfolio Insights)

## Python Study Group — Team-D Portfolio Project


## Project Overview
This project help with;

- Individual asset performance
- Profit and loss
- Net profit/loss after transaction costs and dividend income
- Investment and current portfolio value
- Return percentages
- Performance classifications
- Portfolio-level performance
- Performance ranking
- Profitable and loss-making investments
- Average asset return
- Data quality
- Portfolio allocation
- Asset-type allocation
- Sector exposure
- Country exposure
- Concentration flags
- Portfolio health
- Management-level insights

The project progresses from question-by-question Python exercises into an integrated, reusable mini portfolio analysis system.

> Important: This is an educational project using a fictional dataset. The outputs are descriptive analyses and are not investment recommendations or financial advice.


## Project Objective

The objective of this project is to demonstrate how fundamental Python programming concepts can be combined to solve a practical business and financial-analysis problem.

Rather than treating Python concepts independently, the project applies them progressively to answer a real-world-style analytical question:

`How can raw investment records be transformed into meaningful portfolio performance insights using Python?`


The portfolio analysis system is designed to help an analyst examine investment records and communicate useful descriptive information about:

- Portfolio performance
- Asset-level returns
- Portfolio structure
- Sector exposure
- Geographic exposure
- Data quality
- Defined concentration risks
- Overall portfolio health

The dataset contains fictional assets across Nigeria, Ghana, Kenya, and South Africa, with currencies represented as NGN, GHS, KES, and ZAR.

Currencies are retained as descriptive fields in the supplied dataset and are not converted using exchange rates.


## Dataset

The portfolio contains 20 fictional investment records.

Each investment record contains:

Field| Description
“asset_id”| Unique identifier for the investment
“asset_name”| Name of the investment
“asset_type”| Equity, Bond, or ETF
“country”| Country associated with the investment
“sector”| Economic sector
“quantity”| Number of units held
“purchase_price”| Price at purchase
“current_price”| Current price in the dataset
“purchase_date”| Investment purchase date
“currency”| Currency associated with the record
“transaction_cost”| Transaction-related cost
“dividend_income”| Dividend income received

``` The portfolio is represented using:
Portfolio = [
    {
        “asset_id”: “AST001”,
        “asset_name”: “Alpha Energy”,
        “asset_type”: “Equity”,
        ...
    }
]
```
This structure allows the same calculations to be performed across multiple investment records without creating separate variables for every asset.

## Core Calculations

`1.	Initial Investment
`
Initial Investment =
Quantity × Purchase Price

This represents the amount initially committed to an investment.

`2.	Current Value
`
Current Value =
Quantity × Current Price

This estimates the current value of the asset using the supplied dataset.

`3.	Basic Profit/Loss
`
Profit/Loss =
Current Value – Initial Investment

This provides the basic price-based gain or loss.

`4.	Net Profit/Loss
`
The integrated system additionally considers transaction costs and dividend income:

Net Profit/Loss =
Current Value
−	Initial Investment
−	Transaction Cost
+ Dividend Income

This provides a more complete descriptive result for each asset within the project’s assumptions.

`5.	Return Percentage
`
Return Percentage =
(Net Profit/Loss / Initial Investment) × 100

The return percentage expresses the net result relative to the original investment.


## Performance Classification

Each asset is classified according to its calculated return:

``` Return| Classification
≥ 15%| Excellent
5% – <15%| Positive
0% – <5%| Low Positive
< 0%| Loss
```
These categories are project-defined analytical labels rather than real-world investment ratings.


## Portfolio-Level Analysis

The project moves beyond individual assets to analyse the portfolio as a whole.

The system calculates:

- Total Initial Investment

- The combined initial investment across all 20 records.

- Total Current Value

The combined current value of all assets.

- Total Net Profit/Loss

The combined net result after transaction costs and dividend income.


## Overall Portfolio Return

``` Portfolio Return =
Total Net Profit/Loss / Total Initial Investment × 100
```

## Performance Breakdown

The system also counts how many assets fall into each performance category.


## Extended Portfolio Analysis

### Performance Ranking

Assets are ranked according to their calculated return percentage.

This allows the system to identify the highest and lowest performing assets within the fictional dataset.


**Profitable vs Loss-Making Investments**

The system counts:

- Profitable investments
- Loss-making investments

This provides a quick view of the distribution of positive and negative results.


### Average Asset Return

The system calculates the simple average of individual asset returns.

This is different from the overall portfolio return because the portfolio return reflects the total amount invested, while the simple average gives each asset equal weight.


## Data Quality

The project includes basic validation rules.

The system checks whether:

```Quantity > 0
Purchase Price > 0
Current Price >= 0
```
A deliberately invalid test asset is also created to demonstrate that the validation logic can detect incorrect data without adding the invalid record to the main portfolio.

The main portfolio is designed to contain zero invalid fields under these validation rules.


## Portfolio Allocation

The system examines how the portfolio is distributed across different dimensions.

### Asset Weight

For each asset:

Portfolio Weight =
Asset Current Value / Total Current Portfolio Value × 100

This identifies how much of the portfolio’s current value is represented by each investment.

## Concentration Flag

The project defines a simple concentration screening rule:

«An individual asset representing more than 30% of the portfolio triggers a concentration flag.»

This is a project-defined screening threshold, not an investment recommendation.


## Asset-Type Analysis

The portfolio contains three asset types:
```
- Equity
- Bond
- ETF
```
The system calculates the current portfolio value associated with each asset type and converts those values into allocation percentages.

## Dataset Result

``` Asset Type| Current Value| Approx. Allocation
Equity| 1,799,550| 54.75%
Bond| 996,300| 30.31%
ETF| 491,250| 14.94%
```

## Sector Analysis

The system groups current portfolio value by sector.

The dataset contains the following sectors:

- Energy
- Banking
- Telecom
- Government
- Diversified
- Consumer
- Technology
- Mining

This demonstrates how dictionaries can be used as dynamic accumulators rather than creating separate variables for every sector.


## Country Analysis

The system also examines portfolio exposure by country.

Countries represented include:

- 🇳🇬 Nigeria
- 🇬🇭 Ghana
- 🇰🇪 Kenya
- 🇿🇦 South Africa

## Dataset Result

Country| Current Value| Approx. Allocation
Nigeria| 1,570,550| 47.78%
Ghana| 599,050| 18.22%
Kenya| 588,000| 17.89%
South Africa| 529,500| 16.11%

These figures describe the supplied fictional dataset and should not be interpreted as portfolio recommendations.


## Nested Loops

The project demonstrates both:

`Nested “for” loop`

An outer loop iterates through countries while an inner loop examines portfolio assets belonging to each country.

For country in countries:

    Country_total = 0

    For asset in portfolio:

        If asset[“country”] == country:
            ...

Nested “while” loop

The same country-level analysis is also demonstrated using nested “while” loops, with index variables controlling the iteration.

This demonstrates two different approaches to processing hierarchical data using fundamental Python concepts.


## Integrated Analysis System

The final stage of the notebook transforms the individual question solutions into reusable functions.

### Core Functions
```
“calculate_asset_metrics()”

Calculates the main performance metrics for an individual asset.
```
Returns:

Initial_investment
Current_value
Net_profit_loss
Return_percentage
Performance


``` “calculate_portfolio_summary()”

Calculates portfolio-wide metrics including:
```
- Total investment
- Total current value
- Total net result
- Portfolio return
- Performance counts


“display_portfolio_report()”

Produces a structured portfolio performance report containing overall and individual asset performance.


“generate_risk_flags()”

Identifies project-defined risk conditions such as:

- Negative asset returns
- Individual asset concentration above 30%
- Country concentration above 50%


``` “calculate_health_score()”

Creates a simple portfolio health indicator starting from:
```
100 points

The project applies penalties for defined conditions such as:

- Invalid data
- Loss-making assets
- Concentration flags

The score is constrained between:

0 and 100

«The health score is a learning exercise and should not be interpreted as a professional portfolio rating.»


“get_best_and_worst()”

Identifies the assets with the highest and lowest calculated returns.


“display_management_summary()”

Converts the analytical results into a concise management-level summary containing:

- Number of investments
- Initial investment
- Current portfolio value
- Net portfolio result
- Overall return
- Profitable assets
- Loss-making assets
- Highest return
- Lowest return
- Defined risk flags
- Portfolio health score


Interactive Portfolio Menu

The final system includes an interactive menu that allows users to select specific analyses.

SMARTINVEST AFRICA
PORTFOLIO PERFORMANCE ANALYSIS SYSTEM

1. Portfolio Summary
2. Asset Performance
3. Best and Worst Performers
4. Asset-Type Allocation
5. Sector Analysis
6. Country Analysis
7. Risk Flags
8. Data Quality
9. Portfolio Health
10. Management Summary
0. Exit

Instead of running every analysis manually, the user can select the information they want to inspect.


Dataset Performance Snapshot

Using the supplied fictional dataset, the integrated calculations produce:

Metric| Result
Investments Analysed| 20
Total Initial Investment| 3,137,500
Total Current Value| 3,287,100
Total Net Profit/Loss| 174,900
Overall Portfolio Return| 5.57%
Average Asset Return| 6.06%
Profitable Assets| 15
Loss-Making Assets| 5

Performance Classification

Category| Number of Assets
Excellent| 1
Positive| 13
Low Positive| 1
Loss| 5

These results are calculated directly from the fictional records supplied in the project notebook.


Performance Highlights

Based on the project’s calculations:

Highest Return

Green Telecom

Approximately:

16.13%

Lowest Return

Unity Bank

Approximately:

-6.30%

Portfolio Result

The fictional portfolio produces a positive net result of:

174,900

With an overall calculated return of approximately:

5.57%

These are descriptive outputs from the supplied dataset and are not recommendations to buy, sell, or hold any investment.


Technologies and Concepts

Technology

- Python
- Jupyter Notebook
- GitHub

Python Concepts

The project demonstrates:

- Variables
- Strings
- Integers and floating-point numbers
- Lists
- Dictionaries
- Boolean values
- Arithmetic operators
- Comparison operators
- Logical operators
- “if”
- “elif”
- “else”
- “for” loops
- “while” loops
- Nested loops
- Functions
- Parameters
- Arguments
- Return values
- Accumulators
- Basic data validation
- Structured console output

No external Python libraries are required for the core project.


Repository Structure

A recommended GitHub repository structure is:

Smart-Investment-Portfolio-Performance-Analysis/
│
├── Smart_Investment_Portfolio_Performance_Analysis_TEAM-D_Project.ipynb
│
├── README.md
│
└── screenshots/
    ├── portfolio-summary.png
    ├── asset-performance.png
    ├── risk-flags.png
    └── interactive-menu.png


How to Run

Option 1 — Jupyter Notebook

Open the notebook in:

- Jupyter Notebook
- JupyterLab
- VS Code
- Google Colab

Run the cells sequentially from the dataset section through the integrated analysis system.


Option 2 — Google Colab

Upload the “.ipynb” file into Google Colab and execute the notebook cells.

No external package installation is required for the core analysis.


Testing Approach

The project uses several testing approaches:

Normal Dataset Testing

The 20 fictional investment records are processed through the analytical calculations.

Invalid Data Testing

A deliberately invalid test asset is used to demonstrate data-quality validation.

Multiple Analytical Views

The same dataset is examined through:

- Individual asset analysis
- Portfolio analysis
- Asset-type analysis
- Sector analysis
- Country analysis
- Risk screening
- Portfolio health
- Management reporting

This provides multiple perspectives on the same underlying data.


Key Learning Outcomes

This project demonstrates an important transition in learning Python:

«From solving individual programming questions to building a reusable analytical system.»

The project shows how simple Python concepts can be combined to solve a structured business problem.

Key lessons include:

1. Breaking a complex problem into smaller analytical tasks.
2. Representing multiple records using lists and dictionaries.
3. Using loops to process repeated calculations.
4. Using accumulators for portfolio totals.
5. Creating functions to reduce repetition.
6. Returning calculated values from functions.
7. Validating data before using it in calculations.
8. Grouping data by asset type, sector, and country.
9. Translating calculations into management-level information.
10. Building an interactive menu around reusable analytical functions.


Future Improvements

The current system is intentionally built around fundamental Python concepts. Future versions could expand its capabilities with:

- Persistent data storage
- CSV/database integration
- Automated data validation
- Currency conversion
- Interactive dashboards
- Data visualisation
- Historical performance tracking
- Portfolio benchmarking
- Advanced risk metrics
- Web-based interface
- Automated reporting
- User authentication
- Cloud deployment

These improvements would move the project from an educational console application toward a more comprehensive portfolio analytics application.


Disclaimer

This project uses a fictional dataset created for educational purposes.

The calculations, performance classifications, concentration thresholds, risk flags, health score, and management observations are part of the project’s learning framework.

They should not be treated as financial advice, investment recommendations, credit ratings, or predictions of future investment performance.

Currencies in the dataset are retained as descriptive fields and are not converted between exchange rates.


Acknowledgements

This project was completed as part of the Python Study Group by Team-D.

Special recognition to Coach Timothy for the practical learning framework and guidance provided throughout the project.

Recognition is also given to SmartBizCrux as requested in the project submission guidelines.


Team-D

Team-D — Python Study Group

Project Focus

Portfolio Performance Analysis System

Case Study

SmartInvest Africa

Project Type

Educational / Python Analytics Project


Connect and Collaborate

This repository represents a practical learning project and an evolving step toward applying Python to business and analytical problems.

Feedback, suggestions, and constructive contributions are welcome.


Project Summary

SmartInvest Africa Portfolio Performance Analysis System

«From raw investment data to actionable portfolio insights — using fundamental Python programming concepts.»
