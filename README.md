# テーブル設計

## users テーブル

| Column             | Type   | Options                 |
| ------------------ | ------ | ----------------------- |
| nickname           | string | null: false             |
| email              | string | null: false unique:true |
| encrypted_password | string | null: false             |
| family_name        | string | null: false             |
| first_name         | string | null: false             |
| family_name_kana   | string | null: false             |
| first_name_kana    | string | null: false             |
| birthday           | date   | null: false             |

has_many :items


## 商品 テーブル 
## items テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| title              | string     | null: false                    |
| summary            | text       | null: false                    |
| publisher_id       | integer    | null: false                    |
| highlight          | text       | null: false                    |
| genre_id           | integer    | null: false                    |
| publication_date   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |

belongs_to :user