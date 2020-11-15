# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| name     | string | null: false |
| namekana | string | null: false |
| birthday | date   | null: false |

### Association

- has_many :items
- has_many :purchases

## item テーブル

| Column      | Type    | Options     |
| ----------- | ------- | ----------- |
| image       | string  | null: false |
| name        | string  | null: false |
| text        | text    | null: false |
| category    | string  | null: false |
| status      | string  | null: false |
| deliveryfee | string  | null: false |
| area        | string  | null: false |
| days        | date    | null: false |
| price       | integer | null: false |

### Association

- belongs_to :user
- belongs_to :purchase

## purchases テーブル

| Column       | Type    | Options     |
| ------------ | ------- | ----------- |
| cardinfo     | string  | null: false |
| date         | date    | null: false |
| securitycode | string  | null: false |
| postcode     | string  | null: false |
| prefectures  | string  | null: false |
| municipality | string  | null: false |
| address      | integer | null: false |
| building     | string  | null: false |
| phonenumber  | integer | null: false |

### Association

- belongs_to :item
