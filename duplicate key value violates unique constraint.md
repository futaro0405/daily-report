# duplicate key value violates unique constraint

```
select setval('テーブル名_重複してるカラム_seq',(select max(id) from テーブル名));
```

## ref
["duplicate key value violates unique constraint"の対応方法](https://qiita.com/SNobu/items/2c97cb264c21a45c65bf)

