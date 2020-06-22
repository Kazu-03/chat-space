# usersテーブル

|Column|Type|Optinos|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

### Association
- has_many :departments, throuth: :groups_users
- has_many :groups
- has_many :groups_users
- has_many :messages

## groupsテーブル

|Column|Type|Optinos|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :users, :througt: :groups_users
- has_many :users
- has_many :groups_users
- has_many :messages

## messagesテーブル

|Column|Type|Optinos|
|------|----|-------|
|message|text|null: false|
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

# groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user