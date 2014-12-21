---
title: "Calculating compound interest"
author: "Manzil Malla"
highlighter: highlight.js
output: pdf_document
job: null
knit: slidify::knit2slides
mode: selfcontained
hitheme: tomorrow
subtitle: Developing Data Products (Course Project)
framework: io2012
widgets: []
---

## Information Page

The calculater app gives the compound interest on a base amount over the selected period. The interest rate can be compounded daily, weekly, monthly, semi-annually or annually and user can select either one of the options. 

The interest rate can be selected from a range of 0% to 10%.

The period can be selected from a range of 1990 to 2050.

Additionally, user also have the option to include inflation rate, starting from the first year of the period through the end of the period. The inflation rate is assumed to be fixed over this period.

The inflation rate can be selected from a range of 0% to 5%.

--- .class #id 

## Codes for the calculation


```r
##Script for compound rate calculation

compound_amount<-function(principal,rate,start,end,interval,inflation){
  principal*(1+(rate/interval))^(interval*(end-start))*((1+inflation)^(end-start))
}
```

Principal = Initial Base Amount

Start =  First Year of the Period

End = Last Year of the Period

Rate = Interest Rate (Annual)

Interval = Frequency of Compounding

Inflation = Annual Inflation Rate


--- .class #id 


## Web Links

The materials can be found in:

Web app: [https://manzilmalla.shinyapps.io/Developing-Data-Products/]

GitHub Repo: [https://github.com/manzilmalla/Developing-Data-Products]





--- .class #id 

## Example
For example, the table below shows the yearly balance and interest on the principal amount of $1,000 between 2010 through 2015, compounded semi-annually at the annual interest rate of 2.5%. The table also includes the balance and interest with inflation of 1.5% annually.







```r
knitr::kable(files)
```



| year|  balance|  interest| Balance_With_Inflation| Interest_With_Inflation|
|----:|--------:|---------:|----------------------:|-----------------------:|
| 2010| 1000.000|   0.00000|               1000.000|                 0.00000|
| 2011| 1025.156|  25.15625|               1040.534|                40.53359|
| 2012| 1050.945|  50.94534|               1082.710|                82.71016|
| 2013| 1077.383|  77.38318|               1126.596|               126.59629|
| 2014| 1104.486| 104.48610|               1172.261|               172.26129|
| 2015| 1132.271| 132.27083|               1219.777|               219.77725|
