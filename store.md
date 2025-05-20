* 一旦新規作成、更新、削除の処理は、ここを通る。
* formのPOST先の役割を担っている。

<?php
require_once('functions.php');

createData($_POST);
header('Location: ./index.php');






~説明~
送信されたデータ（$_POST）を受け取り、処理（データ作成）を行った後、トップページ（index.php）へ移動する。


require_once('functions.php');
→PHPで他のファイル（functions.php）を一度だけ読み込む。
  ⇨functions.php に定義された関数や変数が使えるようになる。

require_once
・同じファイルの重複読み込み防止
・指定したファイルが存在しない場合、エラーが起こる。


createData($_POST);
→フォームなどから送信されたデータが$_POST入れられる。
  そのデータをcreateData()という関数に渡して処理


header('Location: ./index.php');
→PHPで リダイレクト（ページ遷移）を行うためのコード。
  ⇨PHPスクリプトの処理後、ブラウザに「index.phpに移動」という指示を出している。

header()関数
→HTTP ヘッダー情報を送信

'Location:  '
→指定されたページへ移動させる