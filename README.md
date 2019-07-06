# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|user_name|string|index: true, null:false, unique:true|
|mail|string|null: false|

### Association
- has_many :groups
- has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false|
|image|string||
|timestamps|integer||

### Association
- belongs_to: users
- belongs_to :groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|user_name|string|null: false|

### Association
- has_many: users, through users
- has_one: message


## membersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer||
|user_id|integer||
|group_id|integer||

### Association
- belongs_to: users
- belongs_to: groups