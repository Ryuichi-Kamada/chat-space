## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,index: true|
|email|string|null: false,uique: true|
|password|string|null: false
|password_confirmation|null: false|

### Association
- has_many: messages
- has_many: groups, through: :groups_users


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,index: true,unique: true|

### Association
- has_many: groups_users
- has_many: messages


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|limit:50|
|body|image|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_one: group