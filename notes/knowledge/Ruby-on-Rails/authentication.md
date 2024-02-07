## ユーザー認証の仕組み
### ステートレスについて
HTTPの仕組みがステートレス
１回目のアクセスでログイン認証
１回目のアクセスでは、認証情報からAさんであると特定
２回目のアクセスはだれか特定不能

HTTPプロトコルの情報だけではアクセスしてきたユーザーがログイン済みなのか判断できない

ログインしているかしていないかの情報を持たないことをステートレスという

### セッションについて
１回目のアクセスでログイン認証が通るとプラウザのCookieにセッションIDが保存される

`has_secure_password`の機能を使用
`bcrypt`を使用

```
rails g model user name:string email:string password_digest:string
```