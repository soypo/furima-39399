# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| Nickname           | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| famiry_name        | string | null: false |
| first_name         | string | null: false |
| famiry_name_kana   | string | null: false |
| first_name_kana    | string | null: false |
| birth_year         | string | null: false |
| birth_month        | string | null: false |
| birth_day          | string | null: false |



### Association

- has_many :items
- has_many :buy
- has_many :shipping

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
- belongs_to :users

## buy(購入) テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :
- belongs_to :

## shipping(配送先) テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association

- belongs_to :
- belongs_to :

## comments テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| text   | text       | null: false                    |


### Association

- belongs_to :
- belongs_to :
