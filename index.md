index.php
* 一番最初に表示されるページ。
* ここに新規作成画面へのリンクやTodoの一覧を表示するHTML。

<?php
require_once('functions.php');
?>

<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Home</title>
</head>
<body>
  welcome hello world
  <div>
     <a href="new.php">
       <p>新規作成</p>
     </a>
  </div>
  <div>
    <table>
      <tr>
        <th>ID</th>
        <th>内容</th>
        <th>更新</th>
        <th>削除</th>
      </tr>
      <?php foreach (getTodoList() as $todo): ?>
        <tr>
          <td><?= $todo['id']; ?></td>
          <td><?= $todo['content']; ?></td>
          <td>
            <a href="">更新</a>
          </td>
          <td>
            <form action="store.php" method="post">
              <input type="hidden" name="id" value="">
              <button type="submit">削除</button>
            </form>
          </td>
        </tr>
      <?php endforeach; ?>
    </table>
  </div>
</body>
</html>








~説明~
PHPとHTMLを使って「ToDoリスト管理ページ」のトップ画面を作っている


<?php ?>で囲むと、HTMLの文中にPHPの処理を書くことが可能
<?php echo $todo['id']; ?>　⇨ ⇨ 省略 ⇨ ⇨　<?= $todo['id']; ?>

<?php require_once('functions.php'); ?>
→functions.phpを読み込む。

<?php foreach (getTodoList() as $todo): ?>
→PHPのforeachループでgetTodoList() から取得した「ToDoリスト(配列)」を1件ずつ処理する


<?php endforeach; ?>
→foreach ループの終わり
  PHPのforeachを : (コロン)で書き始めたときは、endforeach;で閉じる。
⇨書き方として : ではなく、{}を使う方法もある。


<td><?= $todo['id']; ?></td> <td>
<?= $todo['content']; ?></td>
→ToDoリストの情報（IDと内容）をテーブルのセルに表示する


<form action="store.php" method="post">
  <input type="hidden" name="id" value="">
  <button type="submit">削除</button>
→ToDoを削除するためのフォーム


