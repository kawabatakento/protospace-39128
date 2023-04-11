# README

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false, unique |
| encrypted_password | string | null: false |
| profile            | text   | null:false  |
| occupation         | text   | null:false  |
| position           | text   | null:false  |

- has_many comments
- has_many prototypes

## comments テーブル

| Column             | Type   | Options     |
| -------------------| ------ | ----------- |
| user               | reference | null: false |
| prototypes         | reference | null:false, foreign_key: true |
| content            | text   | null:false, foreign_key: true |

- belongs_to user
- belongs_to prototype


## prototypes テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| title  | string | null: false |
| catch_copy | text | null:false |
| concept   | text | null: false |

- belongs_to user
- has_many comments