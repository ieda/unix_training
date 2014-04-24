初めてのコマンド
====

コマンドを打ってみる
----

* `ls`と入力してください
    * 多分こんな感じになると思います(以下は私のMacでの例です)

```
$ macmini-ssuzuki:~ ssuzuki$ ls
Desktop
Documents
Downloads
Library
Movies
Music
Pictures
Public
$ macmini-ssuzuki:~ ssuzuki$ 
```

* 今何をしたのか
    * 「カレントディレクトリのファイルやディレクトリの情報を表示した」
    * なんのこっちゃ

用語解説
----

* **ファイル**(file)
    * 一まとめとなるデータの単位
* **ディレクトリ**(directory)
    * 複数のファイルをまとめた概念、構造
    * 「フォルダ」と同じものと考えてOK
    * UNIX(やCUI環境)ではディレクトリと呼ぶことが多い
* **カレントディレクトリ**(current directory)
    * 今自分が作業をしているディレクトリ
    * どこかのフォルダを開いていて、そこで作業をするイメージ

つまり
----

* `ls`は、今作業中のディレクトリにあるファイルやディレクトリを表示するコマンド
    * CUIだとこうしないとどんなファイルが入っているかがわかりません
    * list segmentsの略……らしい……