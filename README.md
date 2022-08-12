# テーブル設計

## comments テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| content   | text       | null: false |
| prototype | references | null: false |
| user      | references | null: false |

## Association

belongs_to :user
belongs_to :prototype

## prototypes テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | null: false |

## Association

has_many :comments
belongs_to :user

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |
| encrypted_password | string | null: false |

## Association

has_many :comments
has_many :prototypes
