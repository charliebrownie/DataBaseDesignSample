# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|name|string|index: true, null:false, unique:true|
|mail|string|null: false|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false|
|image|string||
|timestamps|integer|null: false|

### Association
- has_many: users, through users
- has_many :groups, through groups

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|user_id|string|null: false|
|name|string|null: false|

### Association
- has_many: users, through users
- has_one: message

# imagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|string||

### Association
- has_many: users, through users

