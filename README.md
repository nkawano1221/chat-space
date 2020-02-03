# README

## group_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|email|string|null: false, unique: true|

 ### Association
- has_many :group_users
- has_many :groups, through: :group_users
- has_many :messages

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|

### Association 
- has_many :group_users
- has_many :users, through: :group_users
- has_many :massages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|text|null: false|
|group_id|integer|null: false, foreign_key: true|

### Association 
- belongs_to :user
- belongs_to :group