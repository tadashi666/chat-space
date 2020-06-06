# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique:true|
|password|string|null:false|
|password confirmation|string|null:false|

### Association
- has_many :groups_users 
- has_many :groups, through:groups_users
- has_many :messages



## messagesテーブル.

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|reference|foreign_key: true|
|user_id|reference|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group



## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique: true|

### Association
- has_many :groups_users
- has_many :users,through:groups_users
- has_many :messages



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|users_id|reference|foreign_key:true|
|groups_id|reference|foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user




