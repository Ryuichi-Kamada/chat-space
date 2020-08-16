## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|user_name|string|null: false,add_index:true|
|email|string|null: false,uique:true|
|password|string|null:false
|password confirmation|null:false|

### Association
- has_many: messages


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null:false,foreign_key:true|
|group_name|string|null: false,add_index:true|

### Association
- has_many: users


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
|message_id|integer|null:false,foreign_key:trye|
|message|text|null: false,limit:50|

### Association
- belongs_to :user

