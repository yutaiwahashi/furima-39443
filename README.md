#  データベース設計

## Usersテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| nickname        | string     | null: false                    |
| email           | string     | null: false                    |
| encrypted_password | string   | null: false                    |
| date_of_birth   | date       | null: false                    |
| last_name       | string     | null: false                    |
| first_name      | string     | null: false                    |
| last_name_kana  | string     | null: false                    |
| first_name_kana | string     | null: false                    |

### Association
- User has_many Items
- User has_many Orders

## Itemsテーブル
| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| user          | references | null: false, foreign key       |
| name          | string     | null: false                    |
| description   | text       | null: false                    |
| category      | string     | null: false                    |
| condition     | string     | null: false                    |
| status        | string     | null: false                    |

### Association
- Item belongs_to :user
- Item has_one :order

## Ordersテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| item            | references | null: false, foreign key       |
| buyer           | references | null: false, foreign key       |

### Association
- Order belongs_to :item
- Order belongs_to :buyer

## ShippingAddressesテーブル
| Column            | Type       | Options                        |
| ----------------- | ---------- | ------------------------------ |
| purchase_record   | references | null: false, foreign key       |
| postal_code       | string     | null: false                    |
| prefecture        | string     | null: false                    |
| city              | string     | null: false                    |
| street_address    | string     | null: false                    |
| building_name     | string     |                                |
| phone_number      | string     | null: false                    |
