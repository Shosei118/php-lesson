<?php
require_once('connection.php');

function createData($post)
{
  createTodoData($post['content']);
}

function getTodoList()
{
    return getAllRecords();
}





~説明~
「Todoリスト」の作成・取得のための関数。
実際のDB接続やデータ操作はconnection.php 。


require_once('connection.php');
→connection.php を読み込む。


function createData($post)
{
  createTodoData($post['content']);
}
→createData関数は、引数としてデータを受け取る
 配列のキーcontentの値を取り出し、createTodoData関数に渡す。


function getTodoList()
{
  return getAllRecords();
}
→getTodoList関数は、TODOリストの全データを取得