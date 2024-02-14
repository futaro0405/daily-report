SessionsControllerを作成
```
bin/rails g controller Sessions new
```
loginのroutingを設定
```config/routes.rb
	get '/login', to: 'sessions#new'
	...
```
loginフォーム
```

```
ログインの実行
```ruby:config/routes.rb
	post '/login', to: 'sessions#create'
	...
end
```

```ruby:app/controllers/sessions_controller/rb
class SessionsController < App
```