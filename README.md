# ChatSpace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :chat_groups
- has_many :chat_comments

## chat_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|chat_group_name|text|null: false|
|chat_group_member|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :chat_comments

## chat_commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|chat_group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :tweet
- belongs_to :chat_group