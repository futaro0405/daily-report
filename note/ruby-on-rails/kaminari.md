# kaminari

```Gemfile
gem 'kaminari'
```

```ruby:/app/controllers/**.rb
def index
	@users = User.page(params[:page]).per(10)
end
```