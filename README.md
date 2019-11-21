## userﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique:true|
|email|string|null: false, unique:true|
|password|integer|null: false, unique:true|

### Association
- has_many:items
- has_one:personal, dependent: :destroy
- has_one:phonenumber, dependent: :destroy
- has_one:address, dependent: :destroy
- has_one:credit_card, dependent: :destroy
- has_many:comments

## personalﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|last_name|string|null: false|
|first_name|string|null: false|
|last_namekana|string|null: false|
|first_namekana|string|null: false|
|birth_year|integer|null: false|
|birth_month|integer|null: false|
|birth_day|integer|null: false|
|icon|text|-------|
|introduction|text|-------|
|user_id|reference|foreign_key: true|

### Association
<!-- - has_many:groups, through: :members
- has_many:messages -->

## phonenumberﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|number|integer|null: false|
|user_id|integer|foreign_key:true|

### Association
<!-- - belongs_to:user
- belongs_to:group -->

## Addressﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|postalcode|integer|null: false|
|region|string|null: false|
|city|string|null: false|
|districtnum|string|null: false|
|user_id|reference|foreign_key:true|

### Association
- belong_to:user
- belong_to:group# git-app

## creditﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|creditnumber|integer|null: false|
|limit_year|integer|null: false|
|limit_month|integer|null: false|
|security|integer|null: false|
|user_id|reference|foreign_key|

### Association
- belong_to:user
- belong_to:group# git-app

## itemsﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|detail|text|null: false|
|category_id|reference|foreing_key: true|
|condition_id|reference|foreign_key: true|
|postage_id|reference|foreign_key: true|
|region_id|reference|foreign_key: true|
|saler(user_id)|reference|foreign_key: true|
|buyer(user_id)|reference|foreign_key: true|

### Association
- has_many: images
- has_many: comments
- belong_to: category
- belong_to: condition
- belong_to: postage
- belong_to: region


## imagesﾃｰﾌﾞﾙ
|Column|Type|Options|
|------|----|-------|
|image|text|null: false|
|item_id|reference|foreign_key|

### Association
- belong_to:item
