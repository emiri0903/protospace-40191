# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile            |  text  | null: false |
| occupation         |  text  | null: false |
| position           |  text  | null: false |

### Association

- has_many :comments
- has_many :prototypes

### Association

- belongs_to :comment
- belongs_to :prototype

## comments テーブル

| Column  | Type    | Options                       |
| ------  | ------  | -------------------------     |
| content |   text  | null: false                   |
|prototype|reference| null: false, foreign_key: true|
|  user   |reference| null: false, foreign_key: true|

### Association

- belongs_to :comment
- belongs_to :prototype

## prototypes テーブル

| Column      | Type    | Options                        |
| ----------- | ------- | ------------------------------ |
| title       | string  | null: false                    |
| catch_copy  | text    | null: false                    |
| concept     | text    | null: false                    |
| user        |reference| null: false, foreign_key: true |

### Association

- has_many :comments

### Association

- belongs_to :user
- belongs_to :comments