# 台本のプレーンテキストによる記法について考察する

## 目的
体裁を気にせずに台本を書いて、それをマスターデータとして、以下のことに使いたい。
- 印刷用、ビューア用などにフォーマットする際のソースにする。
- 香盤表の自動生成。
- バージョン管理してテキストで差分を見れるようにする。

## 条件
- テキストエディタで編集できること。
- テキストエディタ上でそこそこ台本っぽく見えること。
- プログラムで処理できる構造になっていること。
    - 人物名の確実な抽出/検索。
    - セリフのない人物を香盤表に出すためのメタデータ。
- エディタによってはシンタックスハイライトやプレビューができること。
    - カスタムで Extension を開発できるなら、しても良い。

### 行の種類
- 題名
- 著者名
- 登場人物見出し
- 登場人物
- 柱1
- 柱2
- 柱3
- ト書き
- セリフ
- エンドマーク (「おわり」など)
- コメント

ルールとして「空行」を必要としても良い。

## 参考
### 記法
- __一般的な Markdown 記法__

    台本の記法で、題名や柱は [Markdown](https://guides.github.com/features/mastering-markdown/) の Header の書き方に倣っても良さそう。  
    ただし、柱と登場人物見出しを区別する方法が必要。

- __テスピス記法__

    [テスピス記法](http://www.momouta.org/m/thespis/doc/rules) は書籍のソースとして使うものなので、要素が多い。  
    ト書きはタブ始まり、セリフは人物名 + タブ始まり。  
    行頭文字で見出しを定義し、見出しはセクションの開始という意味を持つ。  
    空行が構造上の意味を持つ。

- __O's Editor 2 の「台本」(または「台本印刷」) スタイル__

    [O's Editor 2](http://ospage.jp/soft/oseditor2/oseditor2.html) は WYSWYG エディタだが、ソースはプレーンテキスト。  
    行頭文字で柱を定義し、文字の種類で柱の種類を定義している。  
    「台詞開始文字」("「") を含む行はセリフ行となる。

- __Fountain__

    [Fountain](https://fountain.io/) の [記法](https://fountain.io/syntax) は基本的には英語向けだが、工夫すれば日本語にも使えるかも知れない。  
    対応するエディタについては [こちら](https://fountain.io/apps) にまとまっている。  
    VSCode 向けにも [Better Fountain](https://marketplace.visualstudio.com/items?itemName=piersdeseilligny.betterfountain) という拡張機能がある。  
    日本語で使う場合の考察は [こちら](fountain/for_japanese.md) 。

### エディタ
- __Visual Studio Code__
    - [Visual Studio Code](https://code.visualstudio.com/) - 公式サイト
    - [Extending Visual Studio Code](https://code.visualstudio.com/docs/extensions/overview) - Extension の自作について (→ [翻訳中](vscode_extensions/))
