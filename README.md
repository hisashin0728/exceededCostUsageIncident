# exceededCostUsageIncident
Sentinel を用いた Billable データの課金アラートサンプル例

# 画面例
<img width="819" alt="image" src="https://user-images.githubusercontent.com/55295601/227812605-57752b15-fc43-4418-b80f-da827d20e903.png">

# KQL 例
```
Usage
| where TimeGenerated > ago(queryperiod)
| where DataType !endswith "_CL"
| where IsBillable
| summarize DataGB = sum(Quantity / 1024) // Quantity is Mbytes
| where DataGB > 40
```
