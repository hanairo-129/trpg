# README

# テーブル設計

## users テーブル

| Column   | Type    | Options                  |
| ---------| ------- | ------------------------ |
| email    | string  | unique:true, null: false | null: false, default: ""
| password | string  | null: false              | null: false, default: ""
| nickname | string  | null: false              | #ニックネーム

### Association

- has_many :items
- has_many :room_users
- has_many :rooms, through: room_users
- has_many :messages

## items テーブル

| Column                | Type          | Options           |
| --------------------- | ------------- | ----------------- |
| picture_id            | integer       | null: false       |#商品の状態
| user                  | references    | foreign_key: true |

## rooms テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

## room_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user

## messages テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user









This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
