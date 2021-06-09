# AmazonScribe
Structure  for  scraping

API list below is from Amazon:

*Seller*

| API | maximum request quota| restore rate|
| :-----:| :----: | :----: |
| ListMarketplaceParticipations | 15 | 1 req/minute |
| ListMarketplaceParticipationsByNextToken | 15 | 1 req/minute |


*Report*

| API | maximum request quota| restore rate|
| :-----:| :----: | :----: |
|RequestReport| 15 | 1 req/minute |
|GetReportRequestList| 10 | 1 req/45 second |
|GetReport| 15 | 1 req/minute |

*Order*

| API | maximum request quota| restore rate|
| :-----:| :----: | :----: |
|ListOrders| 6 | 1 req/minute |
|ListOredersByNextToken| 6 | 1 req/minute |
|ListOrderItems| 30 | 1 req/2 seconds |
|ListOrderItemsByNextToken| 30 | 1 req/2 seconds |

Finance

| API | maximum request quota| restore rate|
| :-----:| :----: | :----: |
|ListFinancialEventGroups| 30 | 1 req/2 seconds |
|ListFinancialEventGroupsByNextToken| 30 | 1 req/2 seconds |
|ListFinancialEvents| 30 | 1 req/2 seconds |
|ListFinancialEventsByNextToken| 30 | 1 req/2 seconds |