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
| 01/07 | [2024-01-07](2024-01-07.md) | 8 |
| 01/08 | [2024-01-08](2024-01-08.md) | 7 |
| 01/09 | [2024-01-09](2024-01-09.md) | 2 |
| 01/10 | [2024-01-10](2024-01-10.md) | 1 |
| 01/11 | [2024-01-11](2024-01-11.md)  | 1 |
| 01/12 | [2024-01-12](2024-01-12.md)  | 3 |
| 01/13 | [2024-01-13](2024-01-13.md)  | 1 |
^daily

```chart
type: line
id: daily
tension: 0.29
width: 90%
labelColors: false
fill: false
beginAtZero: false
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
```

```dataviewjs
// デイリーフォルダのファイルから「起きた」が含まれる行を取得する
const pagesIncludeTargetLine = dv.pages('"02_Daily"').file.lists
    .where(l => l.text.includes("起きた"));

// ヒットした行を日付ごとの配列にカンマ区切りで格納する
let dataObj = {};
for (const list of pagesIncludeTargetLine) {
	if(dataObj[list.section]){
		dataObj[list.section] += ', ' + list.text;
	} else {
		dataObj[list.section] = list.text;
	}
	
}
// 連想配列になっているものを1次元配列に変換する
let dataArray = Object.entries(dataObj).map(([key, value]) => [key, value]);

// 実際のテーブル出力部分
dv.table(['日付', 'ログ'], dataArray);
```