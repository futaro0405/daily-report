リポジトリをリネームして自分のアカウントは以下で開発する方法
## 1.リポジトリをクローンする
```
git clone xxx
```
## URL変更
```
git remote -v
git remote set-url origin https://github.com/futaro0405/rails_ec.git
git remote -v
```
ref:
[GitHub Docs](https://docs.github.com/ja/get-started/getting-started-with-git/managing-remote-repositories#changing-a-remote-repositorys-url)
## githubで空のリポジトリ作成

## origin削除、追加
```
git remote rm origin
git remote add origin https://github.com/futaro0405/rails_ec.git
```
## push
```
git push -u origin main
```
ref: