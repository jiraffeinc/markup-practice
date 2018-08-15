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
**書く**

### Sass/CSS

#### カスケーディング
**書く**

#### コードの再利用性とその粒度
**書く**

#### 変数のスコープ
**書く**

#### CSS設計
**書く**

これらの問題を解決するために、様々なアーキテクチャが生み出されています  

[BEM](http://getbem.com/introduction/)  
[SMACSS](https://smacss.com/)  
[Flocss](https://github.com/hiloki/flocss)  
[ECSS](http://ecss.io/)  


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

#### 実装方針について
`気をつけたいこと` の内容が守られていればどんなアプローチをとっても構いません  
全てのコードの意図を説明できるように意識して書いてみてください

## NOTE:
reset cssくらいは最初から入れておくべきか
