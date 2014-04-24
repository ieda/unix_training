環境変数と設定ファイル
====

環境変数とは
----

* システム全体に共通する事柄についての設定
    * Macのターミナルにおける環境変数は、ターミナル内でのみ有効
* 予めシステムで決まっている変数がいろいろある
    * 自分で作ることもできる
* 理解せずに適当に変更すると設定が壊れて正常に動かなくなることもあるので注意
    * といっても、ガチガチに身構える必要はないですが
    * 必要なければいじらないようにしましょう

ちょっと実験
----

* `curl --max-time 5 http://google.co.jp`と入力してください
    * インターネットに接続して`http://google.co.jp`の内容を取ってくる命令です

```
macmini-ssuzuki:~ ssuzuki$ curl --max-time 5 http://google.co.jp
curl: (7) Failed to connect to 2404:6800:4004:801::1018: No route to host
macmini-ssuzuki:~ ssuzuki$
```

* 5秒ぐらい経ってからこんなエラーが出たと思います
    * 設定が足りないため、ターミナルからインターネットに接続できないことが原因です

環境変数の表示と設定
----

* `export`と入力してください
    * なんかいろいろ出てきたと思います

```
macmini-ssuzuki:~ ssuzuki$ export
Apple_PubSub_Socket_Render=/tmp/launch-hQ50Db/Render
COLORFGBG='7;0'
COMMAND_MODE=unix2003
DISPLAY=/tmp/launch-IPSsB0/org.macosforge.xquartz:0
GREP_COLOR='1;32'
GREP_OPTIONS='--color=auto --exclude-dir=.cvs --exclude-dir=.git --exclude-dir=.hg --exclude-dir=.svn'
HOME=/Users/ssuzuki
ITERM_PROFILE=Default
ITERM_SESSION_ID=w0t2p0
(以下略)
```

* `export`は、環境変数を設定するコマンドです
    * 単に`export`とだけ入力すると、今設定されている環境変数の一覧を表示します
* 以下のように入力して、環境変数を設定してください
    * プロキシの設定です

```
export http_proxy="http://proxy.val.co.jp:8080"
export https_proxy="http://proxy.val.co.jp:8080"
```

* `export -p http_proxy`と入力してください
    * 指定した環境変数の内容を表示するコマンドです
    * 今設定した内容が表示されたと思います
* もう1度実験。`curl --max-time 5 http://google.co.jp`と入力してください
    * 以下のように出力されればインターネットへの接続は成功です

```
macmini-ssuzuki:~ ssuzuki$ curl --max-time 5 http://google.co.jp
&lt;HTML&gt;&lt;HEAD&gt;&lt;meta http-equiv="content-type" content="text/html;charset=utf-8"&gt;
&lt;TITLE&gt;301 Moved&lt;/TITLE&gt;&lt;/HEAD&gt;&lt;BODY&gt;
&lt;H1&gt;301 Moved&lt;/H1&gt;
The document has moved
&lt;A HREF="http://www.google.co.jp/"&gt;here&lt;/A&gt;.
&lt;/BODY&gt;&lt;/HTML&gt;
macmini-ssuzuki:~ ssuzuki$
```

ターミナルを閉じると……
----

* 一旦`exit`コマンドを入力してターミナルを終了し、もう1度開いてください
* 環境変数`http_proxy`の内容を確認してください
    * あれ、さっき設定した内容が消えてますね……
    * `http://google.co.jp`にアクセスするコマンドもまた失敗してしまいます
* ターミナルで直接コマンドを叩いて設定した内容は、終了すると消えてしまいます
    * 毎回設定しなくて済むように、設定ファイルを使いましょう

.bash_profileの編集
----

* 設定ファイルの1つ、`~/.bash_profile`を編集してみましょう
    * `.bash_profile`は、ターミナルの起動時に実行される設定ファイルです
        * 厳密には違いますが……
    * ホームディレクトリにあると思います。無ければ作ってください
* さっき入力した環境変数の設定コマンドを、ファイルに書いてください
* 編集して保存したら、ターミナルを再起動してください
    * 改めて起動することで、設定ファイルの内容が読み込まれて反映されます
    * ちなみに、`source ~/.bash_profile`と入力しても読み込まれます
* 環境変数を確認し、実験のコマンドを実行してみてください
    * これで常に設定が反映されるようになりました
