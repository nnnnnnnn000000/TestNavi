# API設計書（簡易版）

目的：
- ログイン
- 問題を解く
- 成績を見る

バックエンド：Node.js + Express  
認証方式：セッション

---

## 認証系API

### ユーザー登録
- Method: POST
- URL: /api/auth/register
- Request:
  - email: string
  - password: string
- Response:
  - 200: 登録成功
  - 400: 既に登録済み

---

### ログイン
- Method: POST
- URL: /api/auth/login
- Request:
  - email: string
  - password: string
- Response:
  - 200: ログイン成功
  - 401: 認証失敗

---

### ログアウト
- Method: POST
- URL: /api/auth/logout
- Request:
  - なし
- Response:
  - 200: ログアウト成功

---

## 問題系API

### 問題一覧取得
- Method: GET
- URL: /api/questions
- Response:
  - 問題一覧

---

### 問題詳細取得
- Method: GET
- URL: /api/questions/:id
- Response:
  - 問題文
  - 選択肢

---

### 回答送信
- Method: POST
- URL: /api/answers
- Request:
  - question_id: number
  - selected_choice: string
- Response:
  - 正誤
  - 解説

---

## 成績系API

### 成績取得
- Method: GET
- URL: /api/results
- Response:
  - 点数
  - 平均点
  - 正答率
