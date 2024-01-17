# テーブル設計

## users テーブル

| Column             | Type    | Options                   |
| ------------------ | ------- | ------------------------- |
| nickname           | string  | null: false               |
| email              | string  | null: false, unique: true |
| encrypted_password | string  | null: false               |


### Association

- has_many :goals

## goals テーブル

| Column            | Type         | Options                        |
| ------------------| ------------ | ------------------------------ |
| title             | string       | null: false                    |
| description       | text         | null: false                    |
| user              | references   | null: false, foreign_key: true |

### Association
  
- belongs_to :user
- has_one :achievements

## achievements テーブル

| Column            | Type         | Options                        |
| ------------------| ------------ | ------------------------------ |
| record_id         | integer      | null: false                    |
| review            | text         |                                |
| goal              | references   | null: false, foreign_key: true |

### Association


- belongs_to :goal

