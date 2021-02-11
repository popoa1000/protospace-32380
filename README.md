# README
# テーブル設計

## userテーブル
| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | string | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## commentsテーブル

| Column    | Type      | Options     |
| --------  | ------    | ----------- |
| text      | text       | null: false |
| user      | references | null: false |
| prototype | references | null: false |

### Association

- belongs_to :users
- belongs_to :prototype

## prototypesテーブル

| Column     | Type      | Options     |
| --------   | ------    | ----------- |
| title      | string    | null: false |
| catch_copy | text      | null: false |
| concept    | text      | null: false |
| image      |           | null: false |
| user       | reference | null: false |

### Association

- belong_to :users
- has_many :comments