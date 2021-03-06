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
  ### クイックウィンApp（仮）
# 概要
  ### 楽しみながら目標を達成する、新しい習慣を作るアプリです。小さな目標を達成してモチベーションを高めていき、やがて大きな目標の達成を目指していきます。
# URL

# テスト用アカウント
  * 
# 利用方法
  ### 新規登録→達成したい目標や身に付けたい習慣を入力→『大きな目標』の達成に近づくための『小さな目標』を決める。
# 目指した課題解決
  ###  対象の職業：社会人、学生
  ###  ダイエットや禁煙、資格の勉強などで挫折してしまうという課題
  ###  達成できるまでモチベーションを保つことができないという課題

# 洗い出した要件
- (1)優先順位(高：３、中：２、低：１)
- (2)機能
- (3)目的
- (4)詳細
- (5)ストーリー(ユースケース)
- (6)見積もり(所要時間)

- (1)
- (2)目標を記録するアプリ
- (3)目標の達成と習慣を作ることをお手伝いする。
- (4)大きな目標を達成するために小さな目標を決めて達成し進んでいる感覚を作る。
- (5)ゲーム感覚で楽しみながら目標を達成できる
- (6)1日(8時間)35日(280時間)

## 1
- (1) 3
- (2) 達成したい目標,(メイン)を決める。
- (3) 目標か習慣化したいことを決める。
- (4) 目標や習慣化したいこと（ダイエット、筋トレ、資格取得、勉強、禁煙、禁酒など）を決める
- (5) 最終ゴールを決める
- (6) 5日(40時間)

## 2
- (1) 3
- (2) 目標(サブ)とその難易度と達成度を設定する
- (3) メインの目標を達成するための小さな目標を複数用意する。
- (4) 難易度と達成度は取り組む目標の優先順位を決められる。小さな目標を達成させて『大きな目標に進んでいる感覚』とモチベーションを高めることが目的です。
- (5) ゴールに近づくための目標(小さな一歩)を決める
- (6) 5日(40時間)

## 3
- (1) 3
- (2) 達成できたら記録できる
- (3) 目標の確認ができて達成済みなら記録できる
- (4) 次に取り組む目標が確認できる。達成済みならチェックを入れられる。
- (5) 決めた目標を一覧でき、達成できたら記録する。
- (6) 5日(40時間)

## 4
- (1) 2
- (2) 達成できた時自分のLVが上がる
- (3) モチベーションが上がる、ゲーム感覚で楽しめる
- (4) 達成した時、目標の難易度と達成度の数値分だけ経験値が貰えてLVが上がる仕組みにする。自分のLVがわかるようにする。
- (5) 更新した時LVが上がったことを確認できる。
- (6) 10日(80時間)

## 5
- (1) 1
- (2) SNSに投稿できる
- (3) 目標とレベルを投稿できるようにする。
- (4) 自分の目標とLVを投稿できる。家族や友人、他のユーザーと楽しめたり努力し合える。
- (5) 日々の成果をアウトプットできる。他のユーザーと努力し合える。
- (6) 3日(24時間)

## 6
- (1) 2
- (2) ユーザー管理機能
- (3) LVと目標が個人で違うため必要
- (4) 目標の管理ができるようになる。
- (5) ログインしないと目標の編集と更新ができない
- (6) 7日(56時間)



# 実装したGIFと説明
  * 
# 実装予定の機能
  * 
# データベース設計
![ER図](file:///Users/andoudaichi/Downloads/fd7b6ec063a49eef25efa43fe0a66ce1.png)
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
