絶対パスと相対パス
====

* パスには2種類の表現方法があります

絶対パス
----

* ルートディレクトリからの位置を全て記述したパスを、**絶対パス**(フルパス)という
    * `/Users/ssuzuki/kenshu`など
    * `/`(ルートディレクトリ)から始まっていれば絶対パス
* `cd`コマンドには、絶対パスを指定することもできます
    * 今いる場所からいきなり全然違うディレクトリに飛ぶこともできます
    * 場所がわかっていて、今いる場所から遠いなら絶対パスの方が楽

```
macmini-ssuzuki:~ ssuzuki$ cd /usr/local/bin
macmini-ssuzuki:bin ssuzuki$ pwd
/usr/local/bin
macmini-ssuzuki:bin ssuzuki$ cd /etc/hoge
-bash: cd: /etc/hoge: No such file or directory
macmini-ssuzuki:bin ssuzuki$ cd
macmini-ssuzuki:~ ssuzuki$ pwd
/Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$
```

相対パス
----

* 今いるディレクトリを基準点として記述したパスを、**相対パス**という
    * `/`から始まっていなければ相対パス
    * 今いる場所からの相対的な位置
* `cd kenshu`などと指定していたのは、実は相対パス
    * `kenshu`は、今いるディレクトリの直下にある`kenshu`ディレクトリを指す
* `.`(ドット1つ)や`..`(ドット2つ)は特別な意味を持つ
    * `.`  : 今いるディレクトリ
    * `..` : 今いるディレクトリの1つ上のディレクトリ
    * `...`とかは無い

相対パスの指定
----

* `~/kenshu`ディレクトリの下に、`test1`ディレクトリと`test2`ディレクトリを作ってください
* `test1`ディレクトリの下に、さらに`test11`、`test12`ディレクトリを作ってください
    * こういう状態になるはず

```
kenshu
|-- test1
|   |-- test11
|   `-- test12
`-- test2
```

* ホームディレクトリに移動してください
* `cd kenshu/test2`と入力してください
    * `test2`に移動した
* `cd ../test1/test11`と入力してください
    * `test11`に移動した
* `cd ./../../test2`と入力してください
    * `test2`に移動した
* `cd ~/../../Users/(自分のユーザ名)`と入力してください
    * ホームディレクトリの2つ上のディレクトリの下の`Users/(自分のユーザ名)`ディレクトリ
    * つまり結局ホームディレクトリ

```
macmini-ssuzuki:~ ssuzuki$ pwd
/Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$ cd kenshu/test2
macmini-ssuzuki:test2 ssuzuki$ pwd
/Users/ssuzuki/kenshu/test2
macmini-ssuzuki:test2 ssuzuki$ cd ../test1/test11
macmini-ssuzuki:test11 ssuzuki$ pwd
/Users/ssuzuki/kenshu/test1/test11
macmini-ssuzuki:test11 ssuzuki$ cd ./../../test2
macmini-ssuzuki:test2 ssuzuki$ pwd
/Users/ssuzuki/kenshu/test2
macmini-ssuzuki:test2 ssuzuki$ cd ~/../../Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$ pwd
/Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$
```

* 相対パスは`/`で区切って何階層でも表すことができる
* パスを指定するタイプのコマンドは、基本的に相対パスも絶対パスも使うことができる

パスの補完機能
----

* パスを入力している途中でTABキーを押すと、当てはまるパスを補完してくれます
    * `~`で`cd ken`まで入力してTABを押すと、`cd kenshu/`になる
* 当てはまるものが複数ある場合は途中まで
    * `~/kenshu/`で`cd te`まで入力してTABを押すと、`cd test`になる
    * `test1`と`test2`が両方存在するため
* "Ctrl+r"で、これまで入力したコマンドを検索することができます
    * ややこしいコマンドをまた実行したいときとかに便利
