## users table

| Column             | Type    | Options      |
| ------------------ | ------- | ------------ |
| nickname           | string  | null: false  |
| email              | string  | unique: true |
| password           | string  | null: false  |
| family_name        | string  | null: false  |
| first_name         | string  | null: false  |
| family_name (kana) | string  | null: false  |
| first_name (kama)  | string  | null: false  |
| birthday_year      | integer | null: false  |
| birthday_month     | integer | null: false  |
| birthday_date      | integer | null: false  |

### Association
has_many :items
has_many :buyers


## items table
| Column             | Type       | Option                         |
| ------------------ | ---------- | ------------------------------ |
| title              | string     | null: false                    |
| description        | text       | null: false                    |
| detail_category    | string     | null: false                    |
| detail_status      | string     | null: false                    |
| send_shipping_cost | string     | null: false                    |
| send_place         | string     | null: false                    |
| send_days          | string     | null: false                    |
| fee                | integer    | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association
belongs_to :user
has_one :buyer


## buyers table
| Column         | Type       | Option                         |
| -------------- | ---------- | ------------------------------ |
| credit_card    | integer    | null: false                    |
| deadline_month | integer    | null: false                    |
| deadline_date  | integer    | null: false                    |
| security_code  | integer    | null: false                    |
| postal_code    | integer    | null: false                    |
| todouhuken     | string     | null: false                    |
| sikuchouson    | string     | null: false                    |
| banchi         | string     | null: false                    |
| tatemonomei    | string     | null: false                    |
| tel            | integer    | null: false                    |
| user           | references | null: false, foreign_key: true |
| item           | references | null: false, foreign_key: true |

### Association
belongs_to :user
belongs_to :item