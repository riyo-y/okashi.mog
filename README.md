# テーブル設計

## usersテーブル

| Column      | Type   | Options     |
| ----------  | ------ | ----------- |
| nickname    | string | null: false |
| email       | string | null: false |
| password    | string | null: false |
| profile     | text   | null: false |

has_many :sweets
has_many :comments



## sweetsテーブル

| Column                | Type        | Options                         |
| --------------------- | ----------- | ------------------------------- |
| products_name         | string      | null: false                     |
| price                 | integer     | null: false                     |
| user                  | references  | null: false foreign_key: true   |
| category_id           | integer     | null: false                     |
| comments              | text        | null: false                     |

has_many :comments


## commentsテーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null:false                     |
| user      | references | null: false, foreign_key: true |

belongs_to :user
belongs_to :sweets