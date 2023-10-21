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

| Column         | Type   | Options     |
| -------------- | ------ | ----------- |
| name           | string | null: false |
| detail         | string | null: false |
| category       | string | null: false |
| condition      | string | null: false |
| delivery_fee   | string | null: false |
| area           | string | null: false |
| shipping_day   | string | null: false |
| price          | string | null: false |
| handling_charge| string | null: false |
| profit         | string | null: false |


### Association

- has_many :buy
- has_many :shipping
- belongs_to :user

## buy(購入) テーブル

| Column | Type       | Options     |
| ------ | ---------- | ----------- |
| user   | references | null: false |
| item   | references | null: false |

### Association

- belongs_to :item
- belongs_to :shipping

## shipping(配送先) テーブル

| Column         | Type       | Options     |
| -------------- | ---------- | ----------- |
|post_code       | string     | null: false |
|prefecture      | string     | null: false |
|city            | string     | null: false |
|street_address  | string     | null: false |
|room_number     | string     | null: false |
|telephone       | string     | null: false |


### Association

- has_many :items
- has_many :buys

## comments テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| text   | text       | null: false                    |


### Association

- belongs_to :item
