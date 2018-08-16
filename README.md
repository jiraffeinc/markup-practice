# markup-practice
マークアップ

## はじめに
このリポジトリはマークアップを練習するためのチュートリアルです  
プロダクションコードを書くために重要な部分のみを記載しています。  
(例えばHTMLやSass/CSSの基本的な説明や文法の解説などは省略しています。)  
わからない単語等が出てきたら調べてみてください。  
それでもわからなければSlackなどで聞いてみてください。

## GOAL:
HTMLとSassを使用したマークアップの基礎はもちろん、  
スケーラブルで保守性の高いマークアップができるようになることを目的とします

## 気をつけたいこと
### エンジニアとして
HTMLやCSSはプログラミング言語ではありませんが、  
プログラミングに関する哲学や原則などは当てはまることが多いので意識するとよいと思います  
[プログラマが知るべき97のこと](https://xn--97-273ae6a4irb6e2hsoiozc2g4b8082p.com/)

### HTML
#### セマンティックなマークアップ
[HTMLセマンティクス](https://developer.mozilla.org/ja/docs/Web/HTML/Element)  
HTMLには文章構造を表現する役割があります。  
タグそれぞれに意味や使用条件があるので、正しく理解してセマンティックを意識したマークアップを行いましょう

#### SEO
SEOを意識したマークアップをおこなうことは重要です  
上記セマンティックに加えてエンジニアは下記を気をつけるべきことは下記です  
* 隠しコンテンツをつくらない  
  styleでdisplay: noneにする、font-sizeを0にする、  
  背景色と文字色を同じにするなど人間が読めない状態になっているとペナルティを受ける可能性があります  
* javascriptで動的にテキストを追加するなどもSEO効果が薄くなってしまう可能性があるので、  
  SEO上重要な項目では行わないようにしましょう  

### Sass/CSS

#### カスケーディング
Sassではモジュールやレイアウトごとにファイルを分割していきますが、  
最終的には一つのStyleとして解釈されます  
ファイルを分割していてもカスケーディングのルールを理解して正しく記述していかないと、  
意図しないところで表示が崩れる問題が発生してしまったりします  
  
CSSでは多くのプログラミングで実装されているnamespaceの概念がありません  
多くの場合は、命名規則やファイルの分割ルールを決めることで解決しています  

#### コードの再利用性とその粒度
CSSの文脈でもプログラミングと同じように、  
プロダクトのスケールに耐えられるよう、再利用性を考えて実装する可能性があります  
CSSで難しい点は、UIなのでグロースハックなどの文脈で微妙に違うレイアウトが生まれるなど、  
作成したコンポーネントが100%再利用されるわけではない点です  
  
近年では、再利用するパーツを最小限に留め、コードの重複を許容するECSSのような考え方も生まれています  
ただし、ECSSの文脈においても全てのコードの重複を許すわけではなく、  
HeaderやFooterそしてよく使うmoduleなどは再利用性を意識して記述していきます  
この粒度を決めるのは難しいのですが、
Projectのメンバーでよく議論して一定のポリシーを持って開発することが大切です


#### CSS設計
上記のような問題を解決するために、様々なアーキテクチャが生み出されています  
  
[BEM](http://getbem.com/introduction/)  
[SMACSS](https://smacss.com/)  
[Flocss](https://github.com/hiloki/flocss)  
[ECSS](http://ecss.io/)  
  
これらの設計思想や方法を理解して、本練習に取り入れてみるとよいかもしれません


## TODOs:
### Step0. 何を作るか
練習用にウェブサイトのTOPページのデザインカンプを用意しました  
セマンティックなHTMLとスケーラブルなCSSを意識して作成してみましょう  
カンプは `design` ディレクトリにおいてあります  
jpgとsketchファイルが置いてありますのでご確認ください  

<img src="https://raw.githubusercontent.com/jiraffeinc/markup-practice/master/docs/images/camp.jpg" />

#### 要件
* Google Chrome (最新Ver) で動作すること  
* レスポンシブであること(PCとSPのデザインカンプの表示が1ページで担保されていること)  


### Step1. 環境構築
* [yarn](https://yarnpkg.com/ja/docs/install#mac-stable)と[Node.js](https://nodejs.org/ja/)を適時インストールしてください  
  ※Node.jsのインストールはバージョン管理のできる[nodenv](https://github.com/nodenv/nodenv)などを使用すると良いです

* packageのインストール
ターミナルでプロジェクトルートに移動し、下記操作を行ってください  
```
yarn install
yarn run build
open ./index.html
```

ブラウザに青い文字で `最もイケてるホームページ` と表示されたら環境構築完了です  
<img src="https://raw.githubusercontent.com/jiraffeinc/markup-practice/master/docs/images/env.png" />
### Step2. 開発
下記コマンドで `src/styles/application.sass` が監視されます  
```
yarn run watch
```

#### HTML
`index.html` にTOPのHTMLを記述してください  

#### CSS
`src/styles/application.sass` を起点としてSassで書いてください  
Scss記法に変更しても構いません

#### 画像
`assets/images/` 以下に格納してある画像を使用してください  

#### 実装方針について
`気をつけたいこと` の内容が守られていればどんなアプローチをとっても構いません  
全てのコードの意図を説明できるように意識して書いてみてください

## NOTE:
reset cssくらいは最初から入れておくべきか
