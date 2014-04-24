コマンドの使い方を調べる
----

* 何かをしようとすると、知らないコマンドを使うことがしょっちゅうあります
    * インストールとか設定とか
* 概要だけでもいいので、使うコマンドが何をするものなのかを調べる癖をつけましょう
    * 普段からどんなことができるのかを知っておくことが大切
    * UNIX文化的には「自分でなんとかする」という感じ

### manコマンド

* `man ls`と入力してください
    * コマンドのマニュアルが表示されます
    * 基本英語です
    * `more`と同じで`q`で終了します
    * manualの略

### ぐぐる

* `linux (コマンド名)`とかで検索すれば大抵何かは出る
    * 日本語の解説も多い
* ただし、**別のUNIX系OSにおける説明の場合も多々あるので注意**
    * OSXじゃなくてRedHat系Linuxの内容だったり、はたまたDebian系だったり……
    * コマンドならまだしも、ソフトのインストールとかになるとそれはもう複雑……
* 基本的には参考程度にし、挙動が違ったら対象OSが違う可能性を考えてみる感じ？