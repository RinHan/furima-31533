## users table

| Column             | Type    | Options                   |
| ------------------ | ------- | ------------------------- |
| nickname           | string  | null: false               |
| email              | string  | null: false, unique: true |
| encrypted_password | string  | null: false               |
| family_name        | string  | null: false               |
| first_name         | string  | null: false               |
| family_name_kana   | string  | null: false               |
| first_name_kama    | string  | null: false               |
| birthday           | date    | null: false               |

### Association
has_many :items
has_many :purchase_records


## items table
| Column                | Type       | Option                         |
| --------------------- | ---------- | ------------------------------ |
| title                 | string     | null: false                    |
| description           | text       | null: false                    |
| detail_category_id    | integer    | null: false                    |
| detail_status_id      | integer    | null: false                    |
| send_shipping_cost_id | integer    | null: false                    |
| todouhuken_id         | integer    | null: false                    |
| send_day_id           | integer    | null: false                    |
| fee                   | integer    | null: false                    |
| user                  | references | null: false, foreign_key: true |

### Association
belongs_to :user
has_one :purchase_record


## purchase record table
| Column         | Type       | Option                         |
| -------------- | ---------- | ------------------------------ |
| user           | references | null: false, foreign_key: true |
| item           | references | null: false, foreign_key: true |

### Association
belongs_to :user
belongs_to :item
has_one :address


## address table
| Column          | Type       | Option                         |
| --------------- | ---------- | ------------------------------ |
| postal_code     | string     | null: false                    |
| todouhuken_id   | integer    | null: false                    |
| sikuchouson     | string     | null: false                    |
| banchi          | string     | null: false                    |
| tatemonomei     | string     |                                |
| tel             | string     | null: false                    |
| purchase_record | references | null: false, foreign_key: true |

### Association
belongs_to :purchase_record