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
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :groups_users

##groupsテーブル
|name|integer||
-
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|string|null: false,foreign|
|group_id|string|null: false,foreign_key: true|
### Association
belongs_to :user


<!-- ## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :text
- belongs_to :user -->