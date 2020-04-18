# DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|e-mail|string|null: false|
|password|string|null:false|
### Association
- has_many :groups_users
- has_many :groups, through :groups_users
- has_many :comments

## groups
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Associstion
- has_many :groups_users
- has_many :users, through :groups_users
- has_many :comments

## messages
|Column|Type|Options|
|------|----|-------|
|message|string|
|image|string|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: ture|
### Association
- belongs_to :user
- belongs_to :group

## tweets_users
|Column|Type|Options|
|------|----|-------|
|