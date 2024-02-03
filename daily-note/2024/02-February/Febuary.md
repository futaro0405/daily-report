## Febuary
### statistics

```dataview
table
date, study, score
from "daily-note/2024/02-February"
where file.day >= date("2024-02-01")
　AND file.day <= date("2024-02-29")
sort file.day asc
```

```dataview
table
sum(rows.study) as total,
length(rows) as count,
round(sum(rows.study) / length(rows), 0) as avg
from "daily-note/2024/02-February"
GROUP BY date(date).year + "-" + date(date).month + "-" + date(date).week as date
WHERE rows.date
```

```dataviewjs
const pages = dv.pages('"daily-note/2024/02-February"').filter(p => p.file.name > "2024-02-00" && p.file.name < "2024-02-32").sort(p => p.file.name);

function extract(pages, key) {
  return pages.map(p => p[key]).values
}

const days = pages.map(p => p.file.name).values  
const scores =  extract(pages, 'score')
const studies = extract(pages, 'study')

function scoreChart(terms, data) {
  return {
    type: 'line',
    options: {
	    width: '100%',
		scales: {
			y: {
				beginAtZero: true
			}
		}
	},
    data: {
      labels: terms,
      datasets: [{
        label: 'score',
        data: data,
        backgroundColor: ['rgba(255, 99, 132, 0.1)'],  
        borderColor: ['rgba(255, 99, 132, 1)'],  
        borderWidth: 1,
        tension: 0.2,
		fill: true,
      }]
    }
  }
}

function studyChart(terms, data) {
  return {
    type: 'line',
    options: {
	    width: '100%',
		scales: {
			y: {
				beginAtZero: true
			}
		}
	},
    data: {
      labels: terms,
      datasets: [{
        label: 'time',
        data: data,
        backgroundColor: ['rgba(99, 132, 255, 0.1)'],  
        borderColor: ['rgba(99, 132, 255, 1)'],  
        borderWidth: 1,
		tension: 0.2,
		fill: true,
      }]
    }
  }
}

function barChart(terms, scores, studies) {
  return {
    type: 'bar',
    data: {
      labels: terms,
      datasets: [{
        label: 'scores',
        data: scores,
        borderColor: ['rgba(99, 132, 255, 1)'],
        backgroundColor: ['rgba(99, 132, 255, 0.7)']
      },{
        label: 'studies',
        data: studies,
        borderColor: ['rgba(255, 99, 132, 1)'],
        backgroundColor: ['rgba(255, 99, 132, 0.7)']
      }]
    }
  }
}

const dailyScore = scoreChart(days, scores)
const dailyStudy = studyChart(days, studies)

window.renderChart(dailyScore, this.container)
window.renderChart(dailyStudy, this.container)
```


### 1st
#### 自己評価
00/100
#### 勉強時間
00 h
#### 良かったこと
- text text text
#### 悪かったこと
- text text text
#### 改善すること(ネクストアクション)
- text text text
#### 質問・相談など(もしあれば)
- text text text
#### 感想・来週の目標
- text text text
### 2nd
#### 自己評価
00/100
#### 勉強時間
00 h
#### 良かったこと
- text text text
#### 悪かったこと
- text text text
#### 改善すること(ネクストアクション)
- text text text
#### 質問・相談など(もしあれば)
- text text text
#### 感想・来週の目標
- text text text
### 3rd
#### 自己評価
00/100
#### 勉強時間
00 h
#### 良かったこと
- text text text
#### 悪かったこと
- text text text
#### 改善すること(ネクストアクション)
- text text text
#### 質問・相談など(もしあれば)
- text text text
#### 感想・来週の目標
- text text text
### 4th
#### 自己評価
00/100
#### 勉強時間
00 h
#### 良かったこと
- text text text
#### 悪かったこと
- text text text
#### 改善すること(ネクストアクション)
- text text text
#### 質問・相談など(もしあれば)
- text text text
#### 感想・来週の目標
- text text text
### 5th
#### 自己評価
00/100
#### 勉強時間
00 h
#### 良かったこと
- text text text
#### 悪かったこと
- text text text
#### 改善すること(ネクストアクション)
- text text text
#### 質問・相談など(もしあれば)
- text text text
#### 感想・来週の目標
- text text text
