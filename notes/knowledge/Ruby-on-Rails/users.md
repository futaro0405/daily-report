## Userモデル作成
```
bin/rails g midel user name:string email:string password_digest:string
```
## migration修正
```
def change
	create_table :users do |t|
		t.string :name, null: false
		t.string :email, null: false
		t.string :password_digest, null: false

		t.timestamps
		t.index :email, uniqe: true
	end
end
```
## パスワード
```Gemfile
gem 'bcrypt', '~> 3.1.7'
```

```app/models/user.rb
class User < ApplicationRecord
	has_secure_password
end
```

## Userモデルにadminフラグ追加
```
bin/rails g migration add_admin_to_users
```

```
def change
	add_column :users, :admin, :boolean, default: false, null: false
```