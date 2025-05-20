<?php

ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
set_error_handler('errorHandler');
function errorHandler($errNo, $errStr, $errFile, $errLine)
{
  if ($errNo === E_NOTICE || $errNo === E_WARNING) {
    $errTitle = $errNo === E_NOTICE ? 'Notice' : 'Warning';
    $escapedErrStr = htmlspecialchars($errStr);
    $escapedErrFile = htmlspecialchars($errFile);

    echo '<b>' . $errTitle . '</b>: ' . $escapedErrStr . ' in <b>' . $escapedErrFile . '</b> on line <b>' . $errLine . '</b>';
    exit;
  }

  return false;
}

define('DSN', 'mysql:dbname=php_lesson;host=localhost;unix_socket=/tmp/mysql.sock');
define('DB_USER', 'root');
define('DB_PASSWORD', '1520030118');　//MySQLのパスワード





〜説明〜
エラーを見やすく表示し、データベースに接続するための設定を定義する
データベース接続に必要な情報を定数として定義する。


ini_set('display_errors', 1);
→PHPのエラーを画面に表示する設定。

ini_set('display_startup_errors', 1);
→PHPの起動時のエラーも画面に表示。

error_reporting(E_ALL);
→すべてのエラーを報告する。

set_error_handler('errorHandler');
→エラーが起きた時にPHPの標準の表示ではなく自分で用意した方法で表示。


$errTitle = $errNo === E_NOTICE ? 'Notice' : 'Warning';
→エラーの種類によってタイトルを分ける。


$escapedErrStr = htmlspecialchars($errStr);
$escapedErrFile = htmlspecialchars($errFile);
→セキュリティ対策としてエラーの内容とファイル名をHTMLエスケープする。
⇨HTMLエスケープとは
 特殊な記号をそのまま表示せず、安全に見せるために別の文字列に置き換えること
 もしそのまま画面に出すと…
 ・意図せずHTMLやJavaScriptとして動いてしまう
 ・悪意あるコードが動いてしまう可能性がある


echo '<b>' . $errTitle . '</b>: ' . $escapedErrStr . ' in <b>' . $escapedErrFile . '</b> on line <b>' . $errLine . '</b>';
→エラー情報をわかりやすくHTML形式で表示。


define('DSN', 'mysql:dbname=php_lesson;host=localhost;unix_socket=/tmp/mysql.sock');
→MySQLのphp_lessonデータベースをソケット経由で接続。
 ・データベース名:php_lesson
 ・ホスト:localhost
 ・接続方法：/tmp/mysql.sock というソケットファイルを使って接続