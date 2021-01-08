# README
# テーブル設計

## user テーブル
| Column     | Type   | Option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association
- belongs_to :prototype
- belongs_to :comment

## prototypes テーブル
| Column     | Type       | Option      |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | null: false |

### Association
- has_many :users
- belongs_to :comment

## comments テーブル
| Column    | Type       | Option      |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### Association
- has_many :users
- has_many :prototypes
