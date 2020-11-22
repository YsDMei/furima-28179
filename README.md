# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| nickname           | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| family_name        | string | null: false |
| last_name          | string | null: false |
| family_name_kana   | string | null: false |
| last_name_kana     | string | null: false |
| birthday           | date   | null: false |

### users Association

- has_many :items
- has_many :purchases

## items テーブル

| Column         | Type    | Options           |
| -------------- | ------- | ----------------- |
| user_id        | integer | foreign_key: true |
| name           | string  | null: false       |
| text           | text    | null: false       |
| category_id    | integer | null: false       |
| status_id      | integer | null: false       |
| deliveryfee_id | integer | null: false       |
| area_id        | integer | null: false       |
| days_id        | integer | null: false       |
| price          | integer | null: false       |

### items Association

- belongs_to :user
- has_one :purchase

## purchases テーブル

| Column  | Type    | Options           |
| ------- | ------- | ----------------- |
| user_id | integer | foreign_key: true |
| item_id | integer | foreign_key: true |

### purchases Association

- belongs_to :user
- belongs_to :item
- has_one :shipping_address

## shipping_addresses テーブル

| Column         | Type    | Options           |
| -------------- | ------- | ----------------- |
| purchase_id    | integer | foreign_key: true |
| postcode       | string  | null: false       |
| prefectures_id | integer | null: false       |
| municipality   | string  | null: false       |
| address        | string  | null: false       |
| building       | string  |                   |
| phonenumber    | string  | null: false       |

### shipping_addresses Association

- belongs_to :purchase
