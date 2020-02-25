# DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :messages
- has_many :groups through: :groups_users
- has_many :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group
- has_many :groups_users

##　groupsテーブル
|name|string|null: false|
- has_many :massages
- has_many :users though: :groups_users
- has_many :groups_users
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|string|null: false,foreign_key: true|
|group_id|string|null: false,foreign_key: true|
### Association
users = users.find()
groups = Groups.find()