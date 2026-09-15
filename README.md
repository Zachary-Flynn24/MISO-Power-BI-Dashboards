MISO Large Load Readiness — Power BI Planning Dashboard

A Power BI planning and screening tool developed for the 2026 TechPoint Xtern Challenge with MISO (Midcontinent Independent System Operator).

The project evaluates whether projected generation additions are aligned with rapidly growing large electrical loads across the MISO footprint. The dashboards combine large-load projections, generation interconnection queue data, resource reliability assumptions, historical MISO demand, and scenario-based screening to identify where future grid constraints may emerge.

Core question: Is enough generation being added in the right places, at the right time, and with enough dependable capacity to support projected large-load growth?

Dashboard Preview

1. MISO Large Load Readiness



The opening dashboard summarizes projected large-load growth from 2026–2032.

It highlights:

50.7 GW of projected large-load growth

Peak annual growth of approximately 16.5 GW

2030 as the highest-growth year

Indiana as the largest projected growth state

Annual and cumulative growth patterns

State-by-state concentration of new load

This page establishes the scale and timing of the large-load challenge before comparing demand growth with the generation queue.

2. Generation Queue Readiness



This page analyzes active and pending generation projects expected within the study horizon.

Key views include:

Total active/pending generation queue capacity

Number of projects in the queue

Queue capacity by proposed in-service year

Generation by resource type

Generation by state

Project status, including withdrawn and active/pending projects

The dashboard makes an important distinction between raw interconnection queue capacity and generation that can realistically be expected to support future demand.

3. Load–Generation Alignment



This dashboard compares projected large-load growth directly against active/pending generation queue capacity.

The analysis includes:

Large-load growth versus generation queue capacity by state

Raw generation coverage percentage

State-level generation surplus or shortfall

Year-by-year cumulative alignment

Identification of states below 100% raw queue coverage

Although total queue capacity may appear sufficient at the system level, the dashboard shows that geographic and timing mismatches can still create local readiness problems.

4. Reliability-Adjusted Readiness



Raw nameplate capacity does not represent the amount of dependable capacity available during system peak conditions.

This dashboard applies resource-specific reliability assumptions to proposed generation and compares the resulting capacity against projected large-load growth.

The screening model accounts for differences among technologies such as:

Solar

Wind

Battery storage

Hybrid resources

Natural gas / combined-cycle generation

Nuclear generation

The result is a more realistic view of expected capacity contribution than simply comparing nameplate MW.

The dashboard identifies states whose apparent raw queue coverage falls below projected demand once resource reliability is considered.

5. MISO Large Load Response Framework



The final planning dashboard converts the analysis into a proposed decision framework.

States are classified into readiness tiers based on reliability-adjusted generation coverage:

Readiness Tier

Coverage

General Response

Ready

≥ 125%

Normal study pathway and continued monitoring

Watch

100–124%

Monitor generation milestones and reassess before full ramp

At Risk

75–99%

Firm-service review, flexibility, and targeted generation/transmission study

Critical

< 75%

Concurrent load-generation study and stronger mitigation actions

The framework is designed around a three-step process:

Screen — Evaluate load, generation, timing, and resource reliability.

Route — Assign the project or area to the appropriate readiness pathway.

Revalidate — Update the assessment as load forecasts, generation projects, or assumptions change.

The goal is to support location- and time-specific planning rather than treating every large-load interconnection the same way.

6. MISO Demand & Forecast Performance



This dashboard provides historical operating context using MISO demand and forecast data.

It includes:

Peak MISO demand

Average MISO demand

Peak net generation

Monthly peak demand

Actual demand versus day-ahead forecast

Mean Absolute Percentage Error (MAPE)

This page helps connect long-term planning assumptions with actual system demand behavior and forecast performance.

Project Objectives

The Power BI model was designed to:

Quantify projected large-load growth through 2032

Identify which states experience the greatest new demand

Analyze MISO generation interconnection queue capacity

Separate raw nameplate capacity from reliability-adjusted capacity

Compare generation additions with projected load by state and year

Identify potential geographic and temporal mismatches

Flag states with projected generation shortfalls

Develop a repeatable readiness-screening framework

Translate analysis into actionable planning recommendations

Analytical Approach

The project follows a layered screening process:

Projected Large Loads
        ↓
Generation Interconnection Queue
        ↓
State + In-Service-Year Alignment
        ↓
Resource Reliability Adjustment
        ↓
Available Capacity Margin
        ↓
Readiness Classification
        ↓
Recommended Planning Response

Why the reliability adjustment matters

A proposed 100 MW solar facility and a 100 MW firm thermal resource should not automatically be treated as providing the same amount of dependable peak capacity.

The model therefore applies resource-specific screening assumptions before comparing generation with new demand.

This prevents raw interconnection queue capacity from overstating actual system readiness.

Key Metrics

Examples of metrics used throughout the dashboards include:

Total Projected Large Load GW

Peak Annual Large-Load Growth

Peak Growth Year

Active/Pending Queue GW

Active/Pending Queue Project Count

Queue GW by Resource Type

Queue GW by State

Raw Queue Coverage %

Reliability-Adjusted Queue GW

Adjusted Queue Coverage %

Adjusted Capacity Margin / Shortfall

States Below 100% Coverage

At-Risk Load GW

Readiness Tier

Peak MISO Demand

Average MISO Demand

Day-Ahead Forecast Error (MAPE)

Power BI Features Used

The project uses a combination of:

Power Query for data cleaning and transformation

DAX measures for capacity, growth, coverage, and shortfall calculations

Data relationships across load, generation, geography, date, and resource type

Conditional formatting for state/year risk matrices

Cards and KPI visuals for key planning metrics

Bar and line charts for state and time comparisons

Slicers for interactive filtering

Decision tables for readiness classification and recommended actions

Data Sources

Midcontinent Independent System Operator (MISO)

Used for generation interconnection queue and system-planning information.

Generator interconnection project data

Queue status

Proposed in-service timing

Resource type

State/location information

Reliability-related planning assumptions

Source: https://www.misoenergy.org/

U.S. Energy Information Administration (EIA)

Used for historical system-demand and forecast-related data.

Source: https://www.eia.gov/opendata/

Public Large-Load / Data Center Information

Publicly available large-load and data-center project information was used to help develop future demand projections.

One source used during the project was:

DataCenter.FYI: https://www.datacenter.fyi/

Example Planning Logic

For each state and study year, the model conceptually evaluates:

Reliability-Adjusted Generation Queue
                  -
Projected Large-Load Growth
                  =
Adjusted Capacity Margin

A positive value indicates generation queue capacity exceeds projected large-load growth under the screening assumptions.

A negative value identifies a potential planning shortfall requiring additional review.

The dashboard then converts the result into a readiness tier and recommended planning pathway.

Repository Structure

MISO-Large-Load-Readiness/
│
├── README.md
├── MISO-Large-Load-Readiness.pbix
│
├── images/
│   ├── 01-large-load-readiness.png
│   ├── 02-generation-queue-readiness.png
│   ├── 03-load-generation-alignment.png
│   ├── 04-reliability-adjusted-readiness.png
│   ├── 05-response-framework.png
│   └── 06-demand-forecast-dashboard.png
│
└── data/
    └── README.md

Public repositories should include only datasets that are permitted to be redistributed. API keys, credentials, private files, and restricted datasets should never be committed.

Key Takeaway

The primary finding of this project is that system-wide generation totals alone are not enough to determine large-load readiness.

Even when aggregate proposed generation exceeds projected load growth, significant risk can remain because of:

Project withdrawals

In-service timing

Geographic mismatch

Resource type

Reliability contribution

Transmission deliverability

Concentrated large-load growth

A useful planning screen therefore needs to evaluate where, when, and how reliably generation capacity is expected to become available.

Future Development

Potential future improvements include:

County-level analysis

Transmission-owner and substation-level screening

Transmission deliverability constraints

Automated EIA and MISO data refreshes

Generator project completion probabilities

Large-load project completion probabilities

More detailed seasonal reliability modeling

Scenario sliders for assumptions

Economic and transmission-upgrade analysis

Automated alerts for states moving between readiness tiers

Disclaimer

This project was developed as part of the 2026 TechPoint Xtern Challenge and is a planning and visualization prototype.

It is not an official MISO planning tool, reliability assessment, transmission study, or forecast. Results depend on the public datasets, screening assumptions, and modeling choices used in the project.

Author

Zachary Flynn
Electrical Engineering
Rose-Hulman Institute of Technology

2026 TechPoint Xtern Challenge — MISO
