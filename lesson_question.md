Section11

Q1
require_once()は何のために記述しているか説明してください。
  同じファイルを一度だけ読み込む

Q2
connectPdo() の返り値は何か、またこの記述は何をするための記述か説明してください。
  返り値：PDOオブジェクト
  データベースに接続してSQL文の実行を行うための準備をする


Q3
try catchとは何か説明してください。
  エラー発生時、プログラムが止まらずに安全に処理を続けるもの

Q4
PDOクラスをインスタンス化する際にtry catchが必要な理由を説明してください。
  例外が発生したときにも正しく動くように対処する必要があり、例外処理という処理を実装する為





Section12

データの受け取り・受け渡しの処理を記述するのはどのファイルでしたか？
① functions.php     ② connection.php     ③ config.php     ④ store.php
  正解：④ store.php
  フォームなどから送信されたデータを受け取り、DBに保存する処理を行う


DB操作処理を記述するのはどのファイルでしたか？
① functions.php     ② connection.php     ③ config.php     ④ store.php
  正解：④ store.php


アプリケーションの設定を記述するのはどのファイルでしたか？
① functions.php     ② connection.php     ③ config.php     ④ store.php
  正解：③ config.php
  アプリケーション全体で使う情報をまとめて管理する


以下のフォームの送信ボタンを押下した際にstore.phpの$_POSTにどんな値が格納されますか？
  <form action="store.php" method="post">
    <input type="text" name="id" value="123">
    <textarea　name="content">焼肉</textarea>
    <button type="submit">送信</button>
  </form>
以下のような連想配列が格納される
  $_POST = [
      'id' => '123',
      'content' => '焼肉'
  ];

header('location: ./index.html')は何をしているか説明してください。
  正解：PHPで自動的にページ移動を行う処理





Section13

connection.phpで定義した変数$dbhの中には何を格納したでしょうか？
① PDO文字列     ② PDOクラス     ③ PDO配列     ④ PDOインスタンス
  ④ PDOインスタンス

<?= $var; ?>は以下の選択肢のうち、どの処理の省略形ですか？
① <php>$var</php>     ② <?php echo $var; ?>     ③ <?php var_dump($var) ?>     ④ <?php $var; ?>
  ② <?php echo $var; ?>

一覧ページにTODOを表示するために今回行ったこととして間違っている選択肢はどれですか？
① 一覧取得の関数が使えるように、index.phpでrequire_onceを使ってfunctions.phpを読み込んだ。
② indexページでPHPが使えるようにファイルの拡張子を変更した。
③ SELECT文でDBからデータを取得した。
④ echoはPHPとHTMLが混在しているときは使えないので短縮表現を使った。
  ④ echoはPHPとHTMLが混在しているときは使えないので短縮表現を使った。

queryメソッドの返り値のデータ型は以下の選択肢のうちどれでしょうか？
① PDOインスタンス     ② 連想配列     ③ PDOStatementインスタンス     ④ 文字列
  ③ PDOStatementインスタンス

getTodoList()の返り値について説明してください。
データベースから取得しTODOリストのデータを格納した連想配列の配列