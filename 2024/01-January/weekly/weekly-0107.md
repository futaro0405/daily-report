## 自己評価
40/100
## 勉強時間
22h
## 良かったこと
- 遅くても23時就寝、6時起床のサイクルができた
- 朝起きてジムに行く習慣ができた
- 睡眠の質をよくするために取り組めた
- Obsidianで日報の作業を簡略化できたこと
## 悪かったこと
- 平日の勉強時間が思ったより取れなかったこと
## 改善すること(ネクストアクション)
- 効率的に学習する方法を模索する
- 勉強時間を確保するライフサイクルを確立する
## 質問・相談など(もしあれば)
- 今週は特になし
## 感想・来週の目標
- 来週は時間を見つけて30時間は確保したい
- 下書きの記事が増えてきたので投稿する
## 勉強時間
| Date | Link | time |
| ---- | ---- | ---- |
| 01/07 | [2024-01-07-sample](2024-01-07-sample.md) | 8 |
| 01/08 | [2024-01-08](2024-01-08.md) | 7 |
| 01/09 | [2024-01-09](2024-01-09.md) | 2 |
| 01/10 | [2024-01-10](2024-01-10.md) | 1 |
| 01/11 | [2024-01-11](2024-01-11.md)  | 1 |
| 01/12 | [2024-01-12](2024-01-12.md)  | 3 |
| 01/13 | [2024-01-13](2024-01-13.md)  | 1 |
^daily

```chart
type: line
id: daily
tension: 0.43
width: 92%
labelColors: false
fill: true
beginAtZero: true
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
```

```dataview
table
date, study, score
from "2024/01-January"
where file.day >= date("2024-01-07")
　AND file.day <= date("2024-01-13")
```


```dataviewjs
const k = ["a", "b", "c"]
const d = [
	[100, 10, 50],
	[100, 10, 50],
	[100, 10, 50],
	]
dv.table(k, d)
```

```dataviewjs
const pages = dv.pages('#daily-report').filter(p => p.file.name > ""2024-01-01")

function extract(pages, key) {
  return pages.map(p => p[key]).values
}

const days = pages.map(p => p.file.name).values  
const scores =  extract(pages, 'score')

function scoreChart(terms, data) {
  return {
    type: 'line',
    data: {
      labels: terms,  
      datasets: [{
        label: 'Mark',
        data: data,
        backgroundColor: ['rgba(99, 255, 132, 0.2)'],  
        borderColor: ['rgba(99, 255, 132, 1)'],  
        borderWidth: 1,
      tension: 0.3
      }]
    }
  }
}

const dailyScore = scoreChart(days, scores)

window.renderChart(dailyScore, this.container)

```