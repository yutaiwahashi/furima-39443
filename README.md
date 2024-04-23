

### データベース設計

### Usersテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| id              | integer    |null: false  |
| name            | string     |null: false  |
| email           | string     |null: false  |
| password_digest | string     |null: false  |
| date_of_birth   | date       |null: false  |
### Association
has_many :item

### Itemsテーブル
| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| id            | integer    |null: false                     |
| user_id       | integer    |null: false  foreign_key: true  |
| name          | string     |null: false                     |
| image_url     | string     |null: false                     |
| description   | text       |null: false                     |
| category      | string     | null: false                    |
| condition     | string     |null: false                     |
### Association
has_one :ordets

### ordersテーブル
| Column              | Type       | Options                        |
| ------------------- | ---------- | ------------------------------ |
| id                  | integer    |null: false  |
| buyer_id            | integer    |null: false  |
| item_id             | integer    |null: false, foreign_key: true  |
| quantity            | integer    |null: false  |
| total_price         | decimal    |null: false  |
| status              | string     |null: false  |
| credit_card_number  | string     |null: false  |
| credit_card_expiry  | string     |null: false  |
| credit_card_cvv     | string     |null: false  |

### ShippingAddressesテーブル
| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| id                 | integer    |null: false   |
| purchase_record_id | integer    |null: false   |
| postal_code        | string     |null: false   |
| prefecture         | string     |null: false   |
| city               | string     |null: false   |
| street_address     | string     |null: false   | 
| building_name      | string     |NOT NULL      |
| phone_number       | string     |null: false   |
