# テーブル設計

## comments テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| content   | text       | null: false |
| prototype | references | null: false |
| user      | references | null: false |

## Association

has_many :user
has_many :prototypes

## prototypes テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | null: false |

## Association

has_many :user
belongs_to :comments

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

belongs_to :comments
belongs_to :prototypes
