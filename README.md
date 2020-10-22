# README
<!-- 
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

* ... -->

# アプリ名
  ### クイックウィン（仮）
# 概要
  ### 楽しみながら目標を達成する、新しい習慣を作るアプリです。小さな目標を達成してモチベーションを高めていき、やがて大きな目標の達成を目指していきます。
# URL
  <!-- ![代替テキスト](画像のURL "画像タイトル") -->
# テスト用アカウント
  * 
# 利用方法
  ### 新規登録→達成したい目標や身に付けたい習慣を入力→『大きな目標』の達成に近づくための『小さな目標』を決める。
# 目指した課題解決
  ###  対象の職業：社会人、学生
  ###  ダイエットや禁煙、資格の勉強などで挫折してしまうという課題
  ###  達成できるまでモチベーションを保つことができないという課題

# 洗い出した要件
| **優先順位(高：３、中：２、低：１)**  | **機能**                            | **目的**     | **詳細**              |**ストーリー(ユースケース)**|**見積もり(所要時間)**|
| - | ----------------- | -------------------------------------------- | ----------- | -------------------- | ---------------------|-------------------|
| 3 ||**目標を記録するアプリ**|**楽しくモチベーションを高めて目標を達成と習慣作りができる**|**大きな目標を達成するために小さな目標を決めて達成し進んでいる感覚を作る。**|**ゲーム感覚で楽しみながら目標を達成できる**|**1日(8時間)35日(280時間)**|

| 3 |**達成したい目標,(メイン)を決める。**|**達成したい目標や習慣にしたいことなどを決める**|**目標や習慣（ダイエット、筋トレ、資格取得、勉強、禁煙、禁酒など）を決める**|**最終ゴールを決める**|**5日(40時間)**|

| 3 |**目標(サブ)とその難易度と達成度を設定する**|**達成した時に最終ゴールに一歩近づいた感覚を作らせるため。**|**目標の内容とその目標を達成する難易度と達成感がどれくらい得られるかを決める**|**ゴールに近づくための目標(小さな一歩)を決める**|**5日(40時間)**|

| 2 |**達成できたら記録できる**|**目標を確認できる＋達成したことを記録できる**|**目標が確認でき、達成できたら達成済みとそうでないものとでわかるようにする。**|**決めた目標を一覧でき、達成済みのものにはチェックをいれる。**|**5日(40時間)**|

| 2 |**達成できた時自分のLVが上がる**|**LVの数値だけ今まで積み重ねてきたことを確認できてモチベーションになる。**|**達成した時、目標の難易度と達成度の数値分だけ経験値が貰えてLVが上がる仕組みにする。自分のLVがわかるようにする。**|**更新した時LVが上がったことを確認できる。**|**10日(80時間)**|

| 1 |**SNSに投稿できる**|**モチベーションを上げることができ、他のユーザーと努力し合えたり家族や友人に確認してもらうことができる。**|**目標とレベルを投稿できるようにする。**|**日々の成果をアウトプットできる。他のユーザーと努力し合える。**|**3日(24時間)**|

| 2 |**ユーザー管理機能**|**個別で目標とLVを持っているため必要。**|**目標の管理ができるようになる。**|**ログインしないと目標の編集と更新ができない**|**7日(56時間)**|



# 実装したGIFと説明
  * 
# 実装予定の機能
  * 
# データベース設計
  # ER
# ローカルでの動作方法
  * 

# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
|   name   | string | null: false |
|   email  | string | null: false |
| password | string | null: false |
|family_name|string | null: false |
| name     | string | null: false |
|family_name_show| string | null: false |
| name_show| string | null: false |
| birthday |  date  | null: false |

### Association

- has_many :goals
- has_many :advances



## goal テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| title  | string | null: false |
|  user  | references | null: false, foreign_key: true  |

### Association

- belongs_to :user
- has_many :advance



##  advance テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
|  title   | string | null: false |
|  user    | references | null: false, foreign_key: true  |
|  goal    | references | null: false, foreign_key: true  |

### Association

- belongs_to :goal
- belongs_to :user
