## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|image|string|

### Association
- has_many :groups, throgh: :members
- has_many :massages
  has_many :groups

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|integer|null: false, foreign_key: true|


### Association
- has_many :users, throgh: :members
- has_many :messages
  has_many :users