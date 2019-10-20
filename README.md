# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

<!-- README.mdに記述してほしい項目は以下になります。
テーブル名
カラム名
カラムの型
カラムのオプション（null false制約など）
アソシエーション -->

## users_テーブル
|Column   |Type     |Options                       |
|------   |----     |-------                       |
|name     |string   |null: false, add_index: true  |
|address  |integer  |null: false, unique: true     |

### Association
- has_many :groups_users
- has_many :groups, through: groups_users
- has_many :messages

## groups_テーブル
|Column   |Type     |Options                       |
|------   |----     |-------                       |
|name     |string   |null: false, unique: true     |

### Association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :messages 

## messages_テーブル
|Column   |Type     |Options                       |
|------   |----     |-------                       |
|user_id  |integer  |null: false, foreign_key: true  |
|group_id |integer  |null: false, foreign_key: true  |
|body     |text     |null: false, foreign_key: true|
|imgage   |string   |  |

### Association
- belongs_to :group
- belongs_to :user


## groups_usersテーブル
|Column   |Type     |Options                       |
|------   |----     |-------                       |
|user_id  |integer  |null: false, foreign_key: true|
|group_id |integer  |null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user





* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
