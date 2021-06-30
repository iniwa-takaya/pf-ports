## データベース設計

### users テーブル

| Column            | Type   | Options     |
| ----------------- | ------ | ----------- |
| email             | string | null: false, unique:true |
| encrypted_password| string | null: false |
| name              | string | null: false |
| birth_day         | date   | null: false |
| phone_number      | string | null: false |
| check_id          | integer| null: false |
| nick_name         | string | null: false |

#### Association

- has_many :task_group_users
- has_many :task_groups, through: :task_group_users

### likes テーブル

| Column     | Type       | Options          |
| ---------- | ---------- | ---------------- |
| portfolio  | references | foreign_key: true|
| user       | references | foreign_key: true|

#### Association

- belongs_to :task_group
- belongs_to :user

### portfolios
| Column      | Type      | Options     |
| ----------- | --------- | ----------- |
| title       | string    | null: false |
| start_date  | timestamp | null: false |
| last_date   | timestamp | null: false |
| app_url     | string    | null: false |
| git_url     | string    | null: false |
| purpose     | text      | null: false |
| persona     | text      | null: false |
| user_story  | text      | null: false |
| detail      | text      | null: false |
| user        | references| foreign_key: true|
 
#### Association

- has_many :users
- has_many :users, through: :task_group_users
