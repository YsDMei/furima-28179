# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| name     | string | null: false |
| namekana | string | null: false |
| birthday | string | null: false |

### Association

- has_many :items
- has_many :purchases

## item テーブル

| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| image       | string | null: false |
| name        | string | null: false |
| text        | string | null: false |
| category    | string | null: false |
| status      | string | null: false |
| deliveryfee | string | null: false |
| area        | string | null: false |
| days        | string | null: false |
| price       | string | null: false |

### Association

- belongs_to :user
- belongs_to :purchase

## purchases テーブル

| Column       | Type   | Options     |
| ------------ | ------ | ----------- |
| cardinfo     | string | null: false |
| date         | string | null: false |
| securitycode | string | null: false |
| postcode     | string | null: false |
| prefectures  | string | null: false |
| municipality | string | null: false |
| address      | string | null: false |
| building     | string | null: false |
| phonenumber  | string | null: false |

### Association

- belongs_to :item
