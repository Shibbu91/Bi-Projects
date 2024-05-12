**Intro**: McDonald’s Corporation is an American operator and franchisor of fast food restaurants represented worldwide and the biggest fast food company in the world. Founded in 1940 by Richard and Maurice MacDonald, the company has grown significantly and played a key role in shaping the fast food industry. The brand prides itself on providing consistent, fast, and affordable food. 

I have created a PowerPoint presentation and Power BI dashboard analyzing the financial performance of McDonald's Corporation, the iconic fast-food giant, spanning the years from 2002 to 2022. Over the past two decades, McDonald's has been a cornerstone of the fast-food industry, serving millions of customers worldwide with its diverse menu and efficient service model. This dashboard offers a detailed insight into McDonald's financial journey, showcasing key metrics and trends that have shaped its growth and market position over time.

**Dashboard**:

![image](https://github.com/Shibbu91/Bi-Projects/assets/87035922/1f5d5e09-a5a5-4b9a-b3a0-2a669c085d04)

**DAX Queries**:

Compound Annual Growth Rate (CAGR) = 

var EndingValue = CALCULATE(SUM('Mc D'[Revenue ($B)]),FILTER('Mc D','Mc D'[Year] = 2022))

var BeginningValue = CALCULATE(SUM('Mc D'[Revenue ($B)]),FILTER('Mc D','Mc D'[Year] = 2002))
RETURN
POWER(EndingValue/BeginningValue,1/20)-1

Current Ratio = DIVIDE(SUM('Mc D'[Total assets ($B)]),SUM('Mc D'[Total liabilities ($B)]))

D/E Ratio = 

var ShareholdersEquity = CALCULATE(SUM('Mc D'[Total assets ($B)])-SUM('Mc D'[Total liabilities ($B)]))
RETURN
DIVIDE(SUM('Mc D'[Total debt ($B)]),ShareholdersEquity)

IDL Revenue = SUM('Mc D'[Revenue ($B)])*10/100

IOM Revenue = SUM('Mc D'[Revenue ($B)])*49/100

US Revenue = SUM('Mc D'[Revenue ($B)])* 41/100

Market Price = DIVIDE(SUM('Mc D'[Market cap ($B)]),SUM('Mc D'[Shares Outstanding ($B)]))

Profit = SUM('Mc D'[Revenue ($B)] ) - SUM('Mc D'[Earnings ($B)])

