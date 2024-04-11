## db
![[image-xdb.png]]

| Users        |
| ------------ |
| id           |
| email        |
| password     |
| name         |
| telephone    |
| birth_date   |
| uid          |
| provider     |
| image_avatar |
| image_cover  |
| profile      |
| location     |
| website      |

| Posts   |
| ------- |
| user_id |
| content |
| image   |

| Relationship |
| ------------ |
| follow_id    |
| followed_id  |

| Event |
| ----- |
|       |

```terminal
rails g model Relationship follow_id:integer followed_id:integer
```

```ruby:app/models/relationship.rb
class Relationship < ApplicationRecord
  belongs_to :follow, class_name: "User"
  belongs_to :followed, class_name: "User"
end
```

```ruby:app/models/relationship.rb
class Relationship < ApplicationRecord
  belongs_to :follow, class_name: "User"
  belongs_to :followed, class_name: "User"
end
```

```ruby:app/models/user.rb
has_many :relationships, class_name: "Relationship", foreign_key: "follow_id", dependent: :destroy
has_many :reverse_of_relationships, class_name: "Relationship", foreign_key: "followed_id", dependent: :destroy

# 一覧画面で使う
has_many :followings, through: :relationships, source: :followed
has_many :followers, through: :reverse_of_relationships, source: :follow
```

