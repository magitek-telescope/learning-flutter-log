# 一日目: 環境構築とアプリケーションの作成

<blockquote class="twitter-tweet" data-lang="en"><p lang="ja" dir="ltr">寝る前にまたちょっと <a href="https://twitter.com/hashtag/ALIS?src=hash&amp;ref_src=twsrc%5Etfw">#ALIS</a> のビューアーやってた。トピックの選択のためのUIのベースを組んだので、切り替え契機でデータを取得し直すやつを明日は追加する。 <a href="https://t.co/VOwJoFIXV8">pic.twitter.com/VOwJoFIXV8</a></p>&mdash; potato4d (@potato4d) <a href="https://twitter.com/potato4d/status/1040654555782963200?ref_src=twsrc%5Etfw">September 14, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

- 作業日: 2018/09/14
- 記述日: 2018/09/15

先週くらいから気になって zip ダウンロードとパスを通すところまでだけやってた Flutter をやってみることにした。

普段スマホアプリは作りたいものがなくてやらなくなるので、仕事で関わっている ALIS(https://alis.to) のビューアーを完成させるところをゴールにした。うまくいくと仕事のほうともシナジーがあるし。

## 環境の準備

VSCode の Dart / Flutter プラグインを入れて適当に導入。基本的にVSCode上でプロジェクトのスキャフォールディングまでできるので楽。やったら買って数時間の iPhone7 で動かしてみることにした。

割とホットリロードが無いと実機で作るのはダルいけど、Flutterはその辺安心っぽいので実機でやることにした。

特に躓いたりすることはなかったけど、困惑することはあったのでメモ。

### ホットリロードの有効化

ひとまず全体が動くまでの確認を `flutter run` でやっていたので、これがただのフルビルドだと気づかなかった。

ホットリロードを有効化したデバッグモードは、 Mac だと Fn + F5 を VSCode でやると良い。

## 開発の所感

あとは大体適当に開発を進めた。一日目のメモを書いておく。

### Flutter 所感

だいたい React 。コンポーネント指向だし。

ReactNative + NativeBase が、 Dart になって NativeBase みたいなものじゃなくてもっと十分使えるだけの品質をもった UI コンポーネントがついてくるという感じ。満足するだけの品質の UI をすばやく組めるのが良い。

基本的にクラスベース自体の React で、自分は今の React スタイルよりクラスベースのスタイルのほうが気に入っているので嬉しいところだった。

「 React のあれどうやってやるの？」みたいなのは公式の RN エンジニア向けのドキュメントが死ぬほど役にたった。 `flutter componentDidMount` とかで無限にググってた。

https://flutter.io/flutter-for-react-native/

## Dart 所感

 Dart は洗練された TypeScript という感じの言語仕様をしていて、 Swift が async / await がなくてハゲたり、 Swift が TypeScript みたいなゆるい型定義ではないから API のマッピングが死ぬほどダルいとかの問題が解消されてるので、ネイティブコードを TS の気持ちで書けるというのが個人的には良かった。

やっぱり TypeScript は最終的に JS であるだけあって厳しいところがあるんだけど、DartはもともとがDartVMで動かそうとしていた都合上か、その辺りガッツリ文法が違い良い。

また、やっぱり型システムが個人的にちょうどいい。強すぎず弱すぎず。

あと、名前付きの引数のシステムが最高で、補完が死ぬほど効く。 Ruby の引数記法に型がついてるような感じ。これは Swift も同じ。

## 成果

http のライブラリでデータを取得してそれをエンティティとしてマッピング、ListViewに流し込んで表示してクリックしたら in-app browser が起動するところまでという感じ。冒頭に貼ったところ。

## 明日やること

1. 2 つある ListView のうちの横方向のリストビューの処理を書く
2. 新着／人気記事を切り替えられるようにする
3. 無限スクロールを作ってみる
