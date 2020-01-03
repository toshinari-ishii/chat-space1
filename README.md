## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, add_index : email, unique : true|
|password|string|null: false,|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users




## messageテーブル
|Column|Type|Options|
|------|----|-------|
|image |text | |
|body |text | |
### Association
- belongs_to :user
- belongs_to :group



## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|users|string|null: false|
|group_id |string|null: false|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users






## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group