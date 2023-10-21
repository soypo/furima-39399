# テーブル設計

## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| famiry_name        | string | null: false               |
| first_name         | string | null: false               |
| famiry_name_kana   | string | null: false               |
| first_name_kana    | string | null: false               |
| birth_day          | date   | null: false               |


### Association

- has_many :items
- has_many :buys

## items(商品情報) テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| name           | string     | null: false                    |
| detail         | text       | null: false                    |
| category_id    | integer    | null: false                    |
| condition_id   | integer    | null: false                    |
| delivery_fee_id| integer    | null: false                    |
| area_id        | integer    | null: false                    |
| shipping_day_id| integer    | null: false                    |
| price          | integer    | null: false                    |
| user_id        | references | null: false,foreign_key: true  |


### Association

- has_one :buy
- belongs_to :user

## buys(購入) テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user_id| references | null: false,foreign_key: true  |
| item   | references | null: false,foreign_key: true  |

### Association

- has_many :user
- belongs_to :item
- has_one :shipping

## shippings(配送先) テーブル

| Column         | Type       | Options     |
| -------------- | ---------- | ----------- |
|post_code       | integer    | null: false |
|prefecture      | string     | null: false |
|city            | string     | null: false |
|street_address  | string     | null: false |
|room_number     | string     |             |
|telephone       | integer    | null: false |
|buy             | string     | null: false |


### Association

- belongs_to :buy

## comments テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| text   | text       | null: false                    |


### Association

- belongs_to :item
