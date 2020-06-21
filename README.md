# usersテーブル

|Column|Type|Optinos|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

### Association
- has_many :groups
- has_many :message

## groupsテーブル

|Column|Type|Optinos|
|------|----|-------|
|groupname|string|null: false|
|add-menber|string|

### Association
- belongs_to :user
- has_many :message

## messagesテーブル

|Column|Type|Optinos|
|------|----|-------|
|message|syring|null: false|
|image|text||
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|

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