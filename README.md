# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|email|string|null: false, unique: true|
### Association
- has_many :groups_users
- has_many :messages
- has_many :groups, through: groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :users, through: groups_users
- has_many :messages
- has_many :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|content|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

### groups_usersテーブル
Column Type Options
user_id integer null: false, foreign_key: true
group_id integer null: false, foreign_key: true
##Association
belongs_to :group
belongs_to :user

groupsテーブルとusersテーブルが多対多になっている・・・中間テーブル
columnに外部キーを追加
Type作成。string型かinteger型か
Option作成。４つの制約。



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
