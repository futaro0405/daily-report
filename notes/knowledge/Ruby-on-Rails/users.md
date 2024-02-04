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