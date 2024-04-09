##oh-my-posh
###1. PowerShellの権限設定を変更
oh-my-poshで利用するPowerShellスクリプトを実行できるように権限を変更する。
####1-1 windows tarminalを管理者で実行
####1-2 外部から入手したスクリプトを実行可能にする
```tarminal:windows tarminal
Set-ExcecutionPolicy RemoteSigned
```
###2. oh-my-poshのインストール
oh-my-poshをインストールする。
途中、インストールの許可が何度か求められるので、許可して実行する。
```
Install-Module oh-my-posh -Scope CurrentUser
```