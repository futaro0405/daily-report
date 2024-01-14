## 自己評価
/100
## 勉強時間
32h
## 良かったこと
- xxxxx
## 悪かったこと
- xxxxx
## 改善すること(ネクストアクション)
- xxxxx
## 質問・相談など(もしあれば)
- xxxxx
## 感想・来週の目標
- xxxxx


```dataview
table
date, study, score
from "2024/01-January"
where file.day >= date("{{Date:YYYY-MM-DD}}")
　AND file.day <= date("{{Date:YYYY-MM-DD}}")
```

```dataviewjs
const pages = dv.pages('#daily').filter(p => p.file.name > "2024-01-02").sort(p => p.file.name);

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