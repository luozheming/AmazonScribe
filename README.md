# AmazonScribe
Structure  for  scraping

### API 
list below is from Amazon original website:

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

*Finance*

| API | maximum request quota| restore rate|
| :-----:| :----: | :----: |
|ListFinancialEventGroups| 30 | 1 req/2 seconds |
|ListFinancialEventGroupsByNextToken| 30 | 1 req/2 seconds |
|ListFinancialEvents| 30 | 1 req/2 seconds |
|ListFinancialEventsByNextToken| 30 | 1 req/2 seconds |


### 领域模型设计

同一个data_collection_info会对应多个task,但同一时刻，只有一个task处于运行状态。（目的：为了方便控制抓取频率和步长）

![avatar](./picture/Domain.png)

### 参数配置中心
| field | length | nullable | description | type | example |
| :-----:| :----: | :----: |:----: |:----: |:----:|
| key | 256 | no | 配置唯一标识 | String | 001 |
| channel | 256 | no | 渠道 | String | Amazon |
| group | 256 | no | 配置组唯一标识 | String | 001 |
| action | 256 | no | 对应的API接口 | String | Seller |
| cron | 256 | no | 定时任务cron表达式 | String | 0 0 0 1/7*？ |
| step | 256 | no | 数据采集步长/min | long | 2500 |
| retryTimes | 256 | no | 重试次数 | int | 3 |
| collectionCeil | 256 | no | 离线数据采集上限 | int | 100 |
| collectionFloor | 256 | no | 离线数据采集下限 | int | 0 |
| active | 256 | no | 接口是否开启抓取能力 | boolean | Y |
| maxResultsPerPage | 256 | yes | 每次数据住区页面最大结果 | int | 100 |
| limitPageNum | 256 | yes | 每次最多处理nextToken数目 | int | 5 |




