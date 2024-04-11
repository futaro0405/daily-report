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