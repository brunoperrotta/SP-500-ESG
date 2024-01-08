# S&P500: ESG


# **Dictionary**

The project **[S&P 500: ESG and Financial Analysis](https://lookerstudio.google.com/reporting/140477a4-3273-4e43-bd81-9bde03abfdc5)** contains two main tables with distinct levels of granularity. 

The table 1 presents information on sector, industry and ESG related-data in January 2023, and financial statistics compiled by enterprise listed in the S&P500 (ROA and ROE 2020, 2021, 2022).  

The table 2 refers to the above mentioned information, disclosing the financial performance of each listed enterprise per day in the years 2020, 2021, 2022. 

From both tables, the following explanations are worth mentioning: 

1. ESG Risk (Sustainalytics)
    1. To impose a risk an issue must have a potentially substantial impact on the economic value of a company (financial risk and return profile). The underlying premise is that the world is transitioning to a more sustainable economy and effective management of ESG risks should be associated with superior long-term enterprise value. Some issues are considered material (likely to influence the decisions made by a reasonable investor) from an ESG perspective even if the financial consequences are not fully measurable today.
    2. ESG Risk Rating is based on: annual review of subindustry exposure scores, indicator selection and indicator weights; Regular annual update of company profiles through public disclosure, media, and NGO reports; Robust quality and control process throughout the year, driven by relevant daily-news flow; Company feedback process.
    3. Total ESG Risk Score: Unmanaged risk (unmanageable risk plus management gap) measured on an open-ended scale starting at zero (no risk) and, for 95% of cases, a maximum score below 50. Functions as a single currency for ESG risk, i.e. can be directly compared across all subindustries covered. 
    4. E/S/G cluster scores are linear combinations of MEI (Material ESG issues) scores which entail, for instance, business ethics, human capital, corporate governance.  The ratings framework is supported by 20 material ESG issues that are underpinned by more than 300 indicators and 1,300 data points. 
        - Environment Risk Score: A score indicating the company's environmental sustainability and impact.
        - Social Risk Score: A score assessing the company's societal and employee-related practices.
        - Governance Risk Score: A score reflecting the quality of the company's governance structure.
        - ESG Risk Percentile: The company's rank in terms of ESG risk compared to others.
        - ESG Risk Level: Based on their quantitative scores (see #1), companies are grouped into one of five risk categories

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c6d7b278-db74-4023-848e-2e9b3eec86ae/c1f170c8-1f5b-4576-a4c9-a522793e08a7/Untitled.png)

1. Level of Controversy (Sustainalytics)
    1. We define a controversy as an event or aggregation of events relating to an ESG topic.
    2. Sustainalytics assesses companies’ involvement in incidents with negative environmental, social and governance (ESG) implications.
    3. The Controversy Rating reflects a company’s level of involvement in issues and how it manages these issues.
    4. Incidents are primarily assessed based on the negative environmental and/or social impact of the company activity as well as the reputational risk that this activity poses to the company. Incidents are tracked through various media and NGO sources and typically inform the Controversy Rating for a period of three years. An incident is tied to one company, one location and one date.
    5. An Incident is assessed on two criteria – sustainability impact and reputational risk – and each assessment criteria is scored on a scale of 1 to 10.
        - Sustainability Impact: Severity of the impact, Accountability of the company and Exceptionality of the company’s involvement.
        - Reputational Risk: Notoriety and Exposure
    6. Events are series of isolated or related incidents that pertain to the same ESG issues.
    7. An event is assessed on a scale of 5 levels:
        
        **Category 5 – Severe** The Event has a severe impact on the environment and society, posing serious business risks to the company. This category represents exceptionally egregious corporate behavior, high frequency of recurrence, very poor management of ESG risks, and a demonstrated lack of willingness by the company to address relevant risks.
        **Category 4 – High** The Event has a high impact on the environment and society, posing high business risks to the company. This rating level represents systemic and/or structural problems within the company, weak management systems and company response, and a recurrence of incidents.
        **Category 3 – Significant** The Event has a significant impact on the environment and society, posing significant business risks to the company. This rating level represents evidence of structural problems in the company due to recurrence of incidents and inadequate implementation of management systems or the lack thereof.
        **Category 2 – Moderate** The Event has a moderate impact on the environment and society, posing moderate business risks to the company. This rating level represents low frequency of recurrence of incidents and adequate or strong management systems and/or company response that mitigate further risks.
        **Category 1 – Low** The Event has a low impact on the environment and society, and risks to the company are minimal or negligible.
        
    
2. Financial Data (Yahoo Finance)
    1. **Date:** This column represents the date of the trading day for which the historical data is provided.
    2. **Open:** The opening price of the stock on the given date. This is the price at which the first transaction occurred when the market opened on that day.
    3. **High:** The highest price at which the stock traded during the trading day.
    4. **Low:** The lowest price at which the stock traded during the trading day.
    5. **Close:** The closing price of the stock on the given date. This is the last price at which a trade occurred before the market closed. (The closing price of a stock and the opening price on the next day can be different for several reasons. After-Hours Trading, Overnight Events, Pre-Market Trading, Order Imbalances, Dividends or Corporate Actions, Market Orders)
    6. **Adj Close:** The adjusted closing price takes into account any corporate actions, such as stock splits or dividends, that occurred after the market closed on a given day. It provides a more accurate reflection of the stock's value over time.
    7. **Volume:** The total number of shares traded on the given date. It represents the activity and liquidity in the stock for that particular day.
    8. **Ticker Symbol:** The stock's unique symbol or abbreviation used to identify it on the stock exchange.
    9. **Debt to Equity Ratio (2022)** : The debt-to-equity ratio (D/E ratio) shows how much debt a company has compared to its assets. It is found by dividing a company's total debt by total shareholder equity. A higher D/E ratio means the company may have a harder time covering its liabilities. Can be negative if the company has negative stockholders equity. This scenario happens when a company owes more money to investors than its assets can cover.  
    10. **Return on Equity (2022):** ROE measures the profitability of a company in relation to its equity. In other words, it is the return of the money invested by the stockholders. 
    11. **Return of Assets** **(2022) :** ROA is a ratio that measures how efficiently a company uses its assets to generate profit.

# **Data Cleaning and Transformation**

Surely this project entailed different layers of data cleaning and transformation. The following ones are worth mentioning in case the reader is interested in understanding the project planning as well as relevant categorization patterns:  

- Recalculated the total ESG Score based on E+S+G
- Erased companies without ESG information
- Reclassified ESG Risk Level column according to new total ESG score column (closed intervals to the right; eg. negligible includes “10”)
- Double-checked controversy rate columns in relation to controversy level
- Erased company without controversy information
- Double-checked each column and inserted information on full-time employees for 5 companies and added sector and industry information to one of them (Caterpillar)
- Included financial information:
    - transactioned capital (jan2023)
    - ROE, ROA and Debt_to_equity (2020-2022)
- Erased Ticker ABC due to lack on information on transactioned capital
- Defined companies in categories: Ethical, Opportunist, Concerning
    - Ethical: ESG Risk “Negligible” or “Low” AND Controversy Level “Low” =  63 companies
    - Opportunist: Difference between ESG Risk and Controversy Level skips one category (ESG RISK / CONTROVERSY) = 3 companies
        - “Negligible”/ “Significant”, “High” or “Severe”
        - “Low”/ “High” or “Severe”
        - “Medium”/ “Severe”
    - Concerning: ESG Risk “High” or “Severe” AND Controversy Level “High” or “Severe” = 8 companies
- Created a new column “Average Stock Price” referring to the average stock price per company in January 2023
- Finalized the layout on Looker
- Made the Project Intro on Looker
- Created a new column “Confidence Level” rating companies as Ethical, Opportunists, Concerning and Neutral
- Deleted Company “MCK” (McKesson Corp) from the analysis due to financial contradiction on debt to equity, ROA and ROE. It was categorized as “neutral” as per confidence level
- The analysis remained with 401 companies

<br>
[final table1](https://docs.google.com/spreadsheets/d/1IFvjXz7YbVWwW-AnZU2ayRnXfZCE2KQRG_2jlSiekkE/edit?usp=sharing)
<br>
[final table2](https://docs.google.com/spreadsheets/d/1PXxFgvsZf7Yyq8otCNFohVWGg0dAlMIXMlVaWlTIwh8/edit?usp=sharing)


