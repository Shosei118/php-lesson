<?php
require_once('config.php');

// PDOクラスのインスタンス化
function connectPdo()
{
  try {
    return new PDO(DSN, DB_USER, DB_PASSWORD);
  } catch (PDOException $e) {
    echo $e->getMessage();
    exit();
  }
}

function getAllRecords()
{
  $dbh = connectPdo();
  $sql = 'SELECT * FROM todos WHERE deleted_at IS NULL';
  return $dbh->query($sql)->fetchAll();
}

// 新規作成処理
function createTodoData($todoText)
{
  $dbh = connectPdo();
  $sql = 'INSERT INTO todos (content) VALUES ("' . $todoText . '")';
  $dbh->query($sql);
}







〜説明〜
PHPでPDOを使ってデータベースのTodoデータを操作


require_once('config.php');
→config.phpを読み込む。

try {
  return new PDO(DSN, DB_USER, DB_PASSWORD);
}
→PDOというクラスを使用しデータベースに接続。
接続できたらPDOのインスタンスを返す。


catch (PDOException $e) {
  echo $e->getMessage();
  exit();
}
→接続に失敗したら、エラーメッセージを表示して終了。


function getAllRecords()
{
  $dbh = connectPdo();
  $sql = 'SELECT * FROM todos WHERE deleted_at IS NULL';
  return $dbh->query($sql)->fetchAll();
}
→Todoリストのデータをすべて取り出す関数
1.データベースに接続。
2.todosテーブルから削除されていないデータ（deleted_atが空）だけを選ぶ。
3. SQLを実行してすべてのデータを取り出して配列で返す。



function createTodoData($todoText)
{
  $dbh = connectPdo();
  $sql = 'INSERT INTO todos (content) VALUES ("' . $todoText . '")';
  $dbh->query($sql);
}
→新しいTodoをデータベースに追加する
1.データベースに接続.
2.入力されたTodoの内容をSQL文にしてcontentカラムに追加。
3.SQLを実行してデータベースに保存。