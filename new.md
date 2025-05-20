* 新規作成の画面を表示するためのHTML。

<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>新規作成</title>
</head>
<body>
  <form action="store.php" method="post">
    <input type="text" name="content">
    <input type="submit" value="作成">
  </form>
  <div>
    <a href="index.php">一覧へもどる</a>
  </div>
</body>
</html>






~説明~
新しいデータを入力して送信するページを作成。
送信後はstore.phpで処理。一覧ページはindex.php 。


<html lang="ja">
→ページの言語を日本語に設定。


<form action="store.php" method="post">
→データの送信方法POST（パスワードや個人情報の送信に適している）
→フォームの送信先store.php


<input type="submit" value="作成">
→送信ボタン。ボタンを押すとフォームが送信され、store.php に移動


<form action="store.php" method="post">
  <input type="text" name="content">
  <input type="submit" value="作成">
</form>
→ 「作成」ボタンを押すと、入力されたcontentの値がstore.phpにPOSTとして送られます。