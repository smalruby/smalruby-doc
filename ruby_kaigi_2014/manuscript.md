# 発表原稿「Kids, Ruby, Fun!: Introduction of the Smalruby and the Ruby Programming Shounendan」

 * 高尾宏治(Kouji Takao) <kouji@smalruby.jp>, 本多展幸(Nobuyuki Honda) <nobyuki@smalruby.jp>
 * 0.3版 - 2014年09月17日
 * 改版履歴
   * 0.1版: 2014年09月05日
   * 0.2版: 2014年09月12日
     * 本多担当分を追記
   * 0.3版: 2014年09月17日
     * すべて記述

## タイトル (高尾)

Kids, Ruby, Fun!

Introduction of the Smalruby and the Ruby Programming Shounendan

- - -

Thank you for attending this presentation, let's begin.

## 自己紹介:高尾 (高尾)

高尾宏治/Kouji Takao/@takaokouji/kouji@smalruby.jp

Rubyプログラミング少年団

- - -

I am Kouji Takao, a leader of the Ruby Programming Shounendan, and one of a CRuby commiter.

## 自己紹介:本多 (本多)

本多展幸/Nobuyuki Honda/@nobyuki/nobyuki@smalruby.jp

Rubyプログラミング少年団

- - -

I am Nobuyuki Honda, a chief education officer of the Ruby Programming Shounendan.

It was a short time, speech *in English* This is the end :-)

これからは日本語で話をします（笑）

## 提供 (高尾)

Sponsored by NaCl; Network Applied Communication Laboratory Ltd.

- - -

私たちは二人とも株式会社ネットワーク応用通信研究所、通称NaClの研究員です。このプレゼンテーションに関する交通費・宿泊費はすべてNaClに負担してもらっています。
NaClはまつもとさんが在籍しているということで有名ですが、せっかくの機会なので少しだけNaClの紹介をします。

## NaCl1 (高尾)

NaCl = SIer

- - -

NaClの生業(なりわい)はSystem Integraterです。

## NaCl2 (高尾)

NaCl = about 30 ruby engineer (TODO)

- - -

NaClの約60人の従業員のうち、その半分である30人くらいはRubyを使ったシステム開発に携わっています。

## NaCl3 (高尾)

NaCl = 6 CRuby committer

- - -

NaClにはまつもとさんを含め、6人のCRubyコミッタが在籍しています。

## NaCl4 (高尾)

Please come to visit out NaCl♪

- - -

島根県松江市という、のどかな地方都市でシステム開発をしていることを感じてもらえると思いますので、興味がある方は遊びに来てくださいね。

さて、それでは本題に戻りますね。

## 再び、タイトル (高尾)

Kids, Ruby, Fun!

Introduction of the Smalruby and the Ruby Programming Shounendan

- - -

このプレゼンテーションでは、私たちRubyプログラミング少年団の活動の紹介と、その中でキーとなるスモウルビーについて説明します。

## Rubyプログラミング少年団1 (高尾)

Rubyプログラミング少年団

「一人でも多くの青少年にプログラミングの喜びを！」

「プログラミングを通じて青少年とネット社会との関わり方を考える組織を地域社会の中に！」

- - -

まずは、Rubyルビープログラミング少年団についてですね。

この団体は 「一人でも多くの青少年にプログラミングの喜びを！」「プログラミングを通じて青少年とネット社会との関わり方を考える組織を地域社会の中に！」 を掲げて活動している青少年のための任意団体です。

## Rubyプログラミング少年団2 (高尾)

毎月第3日曜日

一日Rubyプログラミング体験 in 松江

- - -

今は、毎月第3日曜日に親子向けのプログラミング体験教室を開催しています。

## Rubyプログラミング少年団2 (高尾)

スポーツ少年団 = プログラミング少年団

チーム、コーチ、各種大会

- - -

将来は、野球やサッカーのスポーツ少年団(少年団の対訳:boy scout)のように、

 * 各地域にそれぞれの特色を持ったチームがあり、
 * ボランティアのコーチがいて、
 * 地区大会、県大会、全国大会みたいな試合があるような、

そんなプログラミング少年団を作りたいと考えています。

## 海外のプログラミング教育の動向 (本多)

Overseas countries

U.S.: 20,000 Teachers

U.K.: Compulsory education (義務教育)

Estonia, Finland, Singapore...

- - -

ここ2、3年で小中学生に対するプログラミング教育が、国内外で盛り上がってきています。

スモウルビーの詳細に入る前に、少しプログラミング教育の現状を紹介したいと思います。

まず、海外の状況ですが、プログラミング教育がもっとも活発に行われているのはアメリカだと言われています。2014年5月10日のNew York Times ( http://www.nytimes.com/2014/05/11/us/reading-writing-arithmetic-and-lately-coding.html?_r=1 ) の記事によると、昨年の12月以降、プログラミングを授業に取り入れた幼稚園～高校３年生までの教員の数は全米で２万人に上ると報道されていました。また、オバマ大統領がプログラミングの必修化は必要であるとの発言をしており、この流れはますます加速するでしょう

次に、イギリスでは、今月(2014年9月)から、5から16歳までの義務教育の新カリキュラムにプログラミングが正式導入されています。5歳時点で、アルゴリズムの概念の理解や簡単なプログラムの作成・デバッグといった内容が盛り込まれており、かなり本格的な内容になっています。カリキュラムの策定にはGoogle、Microsoftといった企業も参加しているそうです。

最後に、エストニアでは初等教育の1年目からアプリ開発を教えるカリキュラムが実施されています。エストニアはSkypeが生まれた国であることから、IT振興にあたってはMicrosoftから多くの支援を受けているようです。エストニアにおけるIT産業の重要性はかなり高く、プログラミング教育に積極的に取り組んでいます。

その他にも、フィンランドやシンガポールなど多くの国でプログラミング教育を導入する動きが進んでいます。

## 日本のプログラミング教育の動向1 (本多)

プログラミングが必修化

- - -

続いて、日本の動向を紹介します。

日本では、まず、2008年の学習指導要領の改訂により中学校技術家庭科での「プログラムによる計測と制御」が必修化し、2012年度から完全実施となっています。

## 日本のプログラミング教育の動向2 (本多)

生徒1人につき1台の情報端末

- - -

また、2011年に文部科学省が公表した「教育の情報化ビジョン」では、2020年までに生徒1人につき1台の情報端末を配布することが決定しています。

## 日本のプログラミング教育の動向3 (本多)

 * PEG
 * Life is Tech!
 * TENTO

- - -

一方で、民間の活動も活発に行われています。

最近話題になっているのが、PEGと呼ばれるプログラミング学習普及プロジェクトです。PEGは、こども向けのワークショップを開催しているNPO法人のCANVASとGoogleによる協同プロジェクトで、日本全国でのワークショップの開催や合計5000台のRaspberyPIの提供などを行っています。。

これ以外にも、Life is Tech! という団体で実施している5日程度のキャンプ形式や週1の学習塾形式のものや、TENTOという団体が実施している個別指導塾形式のものなどがあります。

海外だけでなく日本でもプログラミング教育が大変盛り上がってきています。

## Scracth (本多)

Scratch

- - -

多くのプログラミングの授業やワークショップではMITが開発している Scratch というビジュアルプログラミング言語が使われています。Scratch のユーザは全世界で200万人以上で、日本の小中学生向けのプログラミング教育のワークショップでは最も多く利用されています。

## スモウルビー1 (高尾)

Ruby = A Programmer's best friend

- - -

みなさんもご存知のようにRubyは「A Programmer's best friend」ですね。それはこれからプログラミングを学ぼうと考えている子どもたちにとっても同じです。

Rubyの

 * シンプルな文法
 * オブジェクト指向
 * ガーベージコレクタ

といった特徴によって、子供たちでも、コンピュータのことをあまり意識することなく、やりたいことを表現することができます。

## スモウルビー2 (高尾)

 * ×アルファベット
 * ×英語
 * ×キーボード操作

- - -

しかしながら、私は中学生に対して約6年間、Rubyを教えてきたのですが、アルファベット、英語、キーボード操作などが難しく、プログラミングが楽しくなる前にやめてしまうということがわかりました。

## スモウルビー3 (高尾)

Scratch -> Smalruby

- - -

そこで、私たちはスモウルビーを開発しました。

## デモ (高尾、本多)

Demo

- - -

早速ですが、スモウルビーがどんなものか、お見せしますね。

(キャラクターを選んで、命令ブロックを配置します。Rubyボタンを、実行ボタンを押すと、バックグラウンドでrubyを実行して、キャラクターが動きます。)

これがスモウルビーです。

## スモウルビーのアーキテクチャ1 (高尾)

Visual Editor: Rails, Blockly

Runtime: DXRuby, dxruby_sdl + Ruby/SDL

Robotics: Arduino + Dino

- - -

スモウルビーのアーキテクチャはこんな感じです。

## スモウルビーのアーキテクチャ2 (高尾)

Visual Editor

Rails, Blockly

- - -

スモウルビーのエディタ機能は、Railsアプリケーションとして実装しています。
命令ブロックの組み合わせでプログラムを作ったり、そこからRubyのソースコードを生成する機能は、Blocklyというライブラリを使って実現しています。

## スモウルビーのアーキテクチャ3 (高尾)

Runtime

DXRuby, dxruby_sdl + Ruby/SDL

- - -

スモウルビーで作成したプログラムは、WindowsではDXRuby、Mac OS XとLinuxではDXRuby互換APIを提供するdxruby_sdlを利用して、2Dグラフィックス、音楽の再生、イベントハンドリングを実現しています。

## スモウルビーのアーキテクチャ4 (高尾)

Robotics

Arduino + Dino

- - -

また、今回は時間の都合で紹介できませんが、Arduinoと、ArduinoをRubyから制御できるDinoというライブラリを使って、ロボット制御を実現しています。

これがスモウルビーのアーキテクチャです。

## Blockly1 (高尾)

ブロック -> Ruby

- - -

スモウルビーを初めて見た方の多くは、命令ブロックの組み合わせでプログラムを作ることができることに驚かれます。
Rubyってこんなに簡単なんですか！？とかね。

## Blockly2 (高尾)

Blockly - A visual programming editor

- - -

実はスモウルビーの命令ブロックに関する処理は、Google製のBlocklyというJavaScriptのライブラリを使って実現しています。

## Blockly2 (高尾)

Blockly

Google Closure library

- - -

BlocklyはGoogle Closure libraryを使って開発されており、依存関係も少なく、コードサイズも小さく、インストールも簡単で、ウェブブラウザで動作する visual programming editor を開発するにはとても使いやすいものになっています。

## Blockly3 (高尾)

Code.org

MIT App Inventor

- - -

また、Code.org でプログラミング教育に使われていたり、MIT App InventorというAndroidアプリ用のIDEで使われていたりするなど、動作実績も十分にあります。

## 命令ブロックの定義 (高尾)

`app/assets/javascripts/blocks/motion.js.coffee.erb`

```JavaScript
Blockly.Blocks['motion_move'] = {
  init: function() {
    this.setColour(208);
    this.interpolateMsg('%1歩動かす',
      ['STEP', ['Number'], Blockly.ALIGN_RIGHT],
      Blockly.ALIGN_RIGHT);
    this.setInputsInline(true);
    this.setPreviousStatement(true);
    this.setNextStatement(true);
  }
};
```

※実際はCoffeeScriptで記述

- - -

それでは、実際にどのようにして命令ブロックを定義するのか見てみましょう。

これは先ほどのデモでお見せしたキャラクターを「10歩動かす」という命令ブロックの定義です。

まずは命令ブロックに'motion_move'という名前をつけて、それを表現するオブジェクトを代入します。
そのオブジェクトのinitプロパティに命令ブロックの初期化処理を記述します。

ここでは、

 * (setColour)青色
 * (interpolateMsg)STEPという名前で数値を表現した命令ブロックを設定できること、そのラベルが「～歩動かす」であること
 * (setInputsInline)それらを横一列に表示すること
 * (setPreviousStatement)この命令ブロックの前に、命令ブロックをくっつけられること
 * (setNextStatement)この命令ブロックのあとに、命令ブロックをくっつけられること

を指定しています。

これだけで、命令ブロックを定義できます。

## 命令ブロック->Ruby (高尾)

`app/assets/javascripts/blocks/motion.js.coffee.erb`

```JavaScript
Blockly.Ruby['motion_move'] = function(block) {
  var arg =
    Blockly.Ruby.valueToCode(this,
      'STEP',
      Blockly.Ruby.ORDER_NONE);
  return 'move(' + arg + ')';
};
```

※実際はCoffeeScriptで記述

- - -

命令ブロックからRubyのコードを生成するには、先ほど定義した命令ブロックのインスタンスを引数にとり、Rubyのコードを表現した文字列を返すメソッドを定義します。

ここでは、STEPに指定した命令ブロックの値を取り出して、move( その値 ) という文字列を作って、それを返しています。

インデントの調整や演算子の優先順位によって括弧でくくったりするのは、Blocklyのフレームワークがやってくれます。

## 命令ブロックの定義とコード生成 (高尾)

Blockly provide
Instruction block and code generator framework.

- - -

このようにスモウルビーでは、Blocklyのフレームワークを使って、命令ブロックの定義、命令ブロックからRubyのコード生成を実現しています。

## 命令ブロックによるプログラミングの限界 (高尾)

Programming with Instruction block

->

Children wanted to be more difficult...

- - -

これで命令ブロックを使ってRubyのプログラミングができるようになりました。

そして、実際に子供たちに使ってもらったところ、面白いことがわかりました。

素数を求めたいとか、やりたいことが決まっているなど、本格的にプログラミングをやりたい子どもは、早いタイミングで命令ブロックによるプログラミングでは満足できなくなり、コードを直接入力したいというのです。

## Ruby->命令ブロック1 (高尾)

move(10) <-> ブロック

- - -

このような経験から、スモウルビーではRubyのコードから命令ブロックに変換できるようにしました。これは他のVisual Programming Editorにはあまり実装されていないスモウルビーの特徴的な機能です。

しかしながら、Blocklyはソースコードから命令ブロックに変換するためのフレームワークは提供していませんので、独自に実装する必要がありました。

## Ruby->命令ブロック2 (高尾)

Ruby -> サーバ -> XML -> クライアント -> Blockly 読み込み -> 命令ブロック

- - -

じゃあ、それ、Rubyで！ってことで、スモウルビーでは、

 * RubyのソースコードをいったんRailsに送って
 * それを解析して
 * 命令ブロックを表現したXMLに変換して
 * ブラウザに返す。
 * それを読み込んで命令ブロックとして表示する、

というようにして、Rubyのソースコードから命令ブロックへの変換を実現しています。

## Ruby->命令ブロック3 (高尾)

At first: Ripper or RubyParser

Currently: Regexp

- - -

このとき、任意のRubyのソースコードをきちんと解析する必要があります。

開発当初は、RipperやRubyParserを使えばできるね♪と考えていたのですが、プログラムが不完全でシンタックスエラーを含む状態だったりすることがあり、実装に時間がかかることがわかりました。そこで、現在は、正規表現で解析しています。

## Ruby->命令ブロック4 (高尾)

`app/models/concerns/ruby_to_block/block/motion_move.rb`

```Ruby
module RubyToBlock
  module Block
    class MotionMove < CharacterMethodCall
      blocknize '^\s*' + CHAR_RE + 'move\((.+)\)\s*$',
                statement: true, inline: true

      def self.process_match_data(md, context)
        md2 = regexp.match(md[type])
        add_character_method_call_block(context, md2[1], new, STEP: md2[2])
        true
      end
    end
  end
end
```

- - -

これが、「～歩動かす」命令ブロックに関するものです。

blocknizeクラスメソッドの第1引数にmove(値)を示す正規表現を指定しています。

また、process_match_dataクラスメソッドで、move(10)から命令ブロックに変換し、context引数に解析結果を格納しています。

add_character_method_call_blockクラスメソッドでは、move(10)が記述されたコンテキストによって、レシーバがどのキャラクターなのかを判断しています。

このように、各APIに対応するクラスを1つずつ定義して、Rubyのソースコードから命令ブロックに変換できるようにしています。

割と大変ですね～。

# 我々の重点目標1 (高尾)

プログラミング > 創造性・論理的思考力

- - -

それでもスモウルビーでは、Rubyのソースコードと命令ブロックを相互に変換できることにこだわっていきたいと考えています。

現在盛り上がっているプログラミング教育の傾向としては、プログラミングはあくまで道具であり、創造性や論理的思考力をはぐくむことを目的としていることが多いのですが、私たちはプログラミングそのものを教えることにより重点を置きたいと考えています。

# 我々の重点目標2 (高尾)

命令ブロック -> ソースコードの直接入力 -> 好きなエディタ

- - -

命令ブロックでプログラムの基礎を学んだあとは、なるべく早いタイミングで直接Rubyのソースコードを入力してプログラムを作成できるようになってほしい。そして、自分の好きなエディタを見つけて、私たちのようなプログラミングが好きなプログラマになってほしいと考えています。

## まとめ1 (高尾)

 * The Ruby Programming Shounendan
 * The current state of programming education
 * Smalruby

- - -

このプレゼンテーションでは、

 * Rubyプログラミング少年団の紹介
 * プログラミング教育の現状
 * スモウルビーの説明

をしました。

## まとめ2 (高尾)

Welcome Developers

https://github.com/smalruby

- - -

スモウルビーは私一人で開発しています。
興味がある方は、ぜひPull Requestをお願いします！

## まとめ3 (高尾)

Welcome Workshop Owners

Facebook:Rubyプログラミング少年団 or e-mail: contact@smalruby.jp

- - -

また、スモウルビーを使って子供向けのワークショップを開催してみたいという人もウェルカムです。

ワークショップの進め方、教科書を含む教材などの情報提供をしますので、気軽に声をかけてください。

## 質疑応答

Q/A

Facebook / Twitter / http://smalruby.jp

- - -

以上で、説明を終わります。なにか質問があるかたはおられますでしょうか？

## おわり (本多)

Ruby = 最高の道具

- - -

自分の生活で使う道具を自分で直すことができる、また、あらたな問題に直面したときにその問題を解決するための道具を自分で作り出すことができることが非常に重要だと考えています。このような価値観はオープンソースソフトウェアに関わっている皆さんには共感していただけるのではないかと思います。

Rubyは問題を解決するための汎用的で強力なツールなので、私たちはこの最高の道具を子ども達に授けたいという想いで活動に取り組んでいきます。

本日は、どうもありがとうございました。
