# DB設計書（MySQL）

---

## users（ユーザー）

| カラム名 | 型 | 説明 |
|--------|----|----|
| id | INT PK AUTO_INCREMENT | ユーザーID |
| email | VARCHAR(255) UNIQUE | メールアドレス |
| password | VARCHAR(255) | パスワード（ハッシュ） |
| created_at | DATETIME | 作成日時 |

---

## questions（問題）

| カラム名 | 型 | 説明 |
|--------|----|----|
| id | INT PK AUTO_INCREMENT | 問題ID |
| question_text | TEXT | 問題文 |
| correct_answer | VARCHAR(50) | 正解 |
| explanation | TEXT | 解説 |

---

## answers（回答履歴）

| カラム名 | 型 | 説明 |
|--------|----|----|
| id | INT PK AUTO_INCREMENT | 回答ID |
| user_id | INT FK | ユーザーID |
| question_id | INT FK | 問題ID |
| selected_answer | VARCHAR(50) | 選択した回答 |
| is_correct | BOOLEAN | 正誤 |
| created_at | DATETIME | 回答日時 |

---

## results（成績）

| カラム名 | 型 | 説明 |
|--------|----|----|
| id | INT PK AUTO_INCREMENT | 成績ID |
| user_id | INT FK | ユーザーID |
| score | INT | 点数 |
| created_at | DATETIME | 作成日時 |
