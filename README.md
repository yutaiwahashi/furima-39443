#  データベース設計

## Usersテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| id              | integer    | null: false, primary key       |
| nickname        | string     | null: false                    |
| email           | string     | null: false                    |
| password_digest | string     | null: false                    |
| date_of_birth   | date       | null: false                    |
| last_name       | string     | null: false                    |
| first_name      | string     | null: false                    |
| last_name_kana  | string     | null: false                    |
| first_name_kana | string     | null: false                    |
### Association
has_many :model


## Itemsテーブル
| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| id            | integer    | null: false, primary key       |
| user_id       | references | null: false, foreign key       |
| name          | string     | null: false                    |
| description   | text       | null: false                    |
| category      | string     | null: false                    |
| condition     | string     | null: false                    |
| status        | string     | null: false                    |
### Association
  belongs_to :user
  has_one :order


## Ordersテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| id              | integer    | null: false, primary key       |
| item_id         | references | null: false, foreign key       |
| buyer_id        | references | null: false, foreign key       |
| quantity        | integer    | null: false                    |
| total_price     | integer    | null: false                    |

## ShippingAddressesテーブル
| Column            | Type       | Options                        |
| ----------------- | ---------- | ------------------------------ |
| id                | integer    | null: false, primary key       |
| purchase_record_id| references | null: false, foreign key       |
| postal_code       | string     | null: false                    |
| prefecture        | string     | null: false                    |
| city              | string     | null: false                    |
| street_address    | string     | null: false                    |
| building_name     | string     |                                |
| phone_number      | string     | null: false                    |
