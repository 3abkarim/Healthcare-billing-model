Healthcare Billing Dimensional Model

A dimensional data model built using Kimball's methodology, implemented as a Galaxy Schema (Fact Constellation) with three fact tables sharing conformed dimensions, delivered as a Power BI dashboard.

Business Processes

Fact TableBusiness ProcessGrainFact_BillingHospital billing revenue & volumeCountry, BU, Month, Department, Payment TypeFact_MarketingDigital marketing revenue & volumeBU, MonthFact_Medical_CRMMedical CRM revenue & volumeBU, Month

Schema Design

The three fact tables share conformed dimensions — BU and Date — while Billing additionally connects to Country, Department, and Payment Type, which are unique to that business process. This makes the model a Fact Constellation rather than a simple Star Schema.

Dimensions:


Dim_Date (Month)
Dim_BU (Hospital / Business Unit)
Dim_Country
Dim_Department
Dim_Payment_Type


Measures per fact table:


Billing: Baseline / Actual / Historical / Target — Volume, C/V, Revenue
Marketing: Baseline / Actual / Target — Revenue, Volume, RPP
Medical CRM: Baseline / Actual / Target — Revenue, Volume, CPV


Dashboard

A Directors-level Power BI dashboard tracks Baseline, Historical, Actual, and Target values with Achievement % and Growth % across Revenue, Volume, and CPV/RPP, with slicers for Country, Business Unit, Month, and Payment Method.

Tools


Power Query (M) for staging, dimensional transformation, and surrogate key generation
Power BI data model with star/galaxy relationships
DAX for KPI measures


File


Andulsia.pbix — full Power BI file (data model + report)
