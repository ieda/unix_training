ファイルの作成と表示
====

新しいファイルの作成
----

* `~/kenshu/test2`に移動してください
* `touch renshu.txt`と入力してください

```
macmini-ssuzuki:~ ssuzuki$ cd ~/kenshu/test2
macmini-ssuzuki:test2 ssuzuki$ touch renshu.txt
macmini-ssuzuki:test2 ssuzuki$ ls
renshu.txt
macmini-ssuzuki:test2 ssuzuki$
```

* `touch (ファイル名)`と入力すると、新しい空のファイルが作成されます
    * `touch`コマンド本来の目的とは異なりますが、新しいファイルを作る方法としてよく使われます
        * 本来の目的が気になる人は調べてみてください
    * ファイルを作る方法自体は他にもいくらでもありますが……

```
# ファイルリスト
kenshu
|-- test1
|   |-- test11
|   `-- test12
`-- test2
    `-- renshu.txt  # 新しいファイル
```

ファイルの編集
----

* `open renshu.txt`と入力してください
    * 「テキストエディット」かなんかのエディタが開いたと思います
* 何か適当に書いて保存してください
* `open`はファイルやディレクトリなどを、なんらかのアプリケーションで開くコマンドです
    * **OSXの独自コマンドなので注意！！**
* ファイル編集の方法もいくらでもありますが、ここでは普通のテキストエディタを使うことにします
    * 使える人はvimとかemacsとか使ってもいいのよ

ファイルの中身を表示する
----

* `cat renshu.txt`と入力してください
    * 今作ったファイルの中身が表示されたと思います
* `cat`コマンドを使うと、指定したファイルの中身が表示されます
    * 複数のファイルを指定すると、それらを結合して出力します
    * catenate(連結する)の略
    * これも微妙に本来の目的とは違いますが、便利なので中身を確認する目的でよく使われます
* では、`cat /var/log/system.log`と入力してください
    * システムで記録されているログファイルです
    * 長いファイルなので、内容が一気にドバーっと流れていったと思います
    * これは見づらい

ファイルの中身をもうちょっと扱いやすく表示する
----

* `more /var/log/system.log`と入力してください
    * ファイルの頭の方だけが表示されたと思います
* returnキーや下キーや上キーを押してみてください
    * スクロールしたと思います
* `more`はファイルの中身を画面サイズに合った分だけ順番に表示するコマンドです
    * 一番下に"More"と表示されているのが由来(OSXの場合は表示されてないけど……)
    * 途中で見るのをやめるときは`q`を押せば元に戻ります
* `more`に似たコマンドに`less`があります
    * 使い方はほとんど同じ
        * `more`よりも高機能
    * `more`の対義語をもじったダジャレ命名コマンド
        * なんかこういう文化があります……
