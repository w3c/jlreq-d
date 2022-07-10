[日本語の説明](#日本語デジタルテキスト組版の要件)は英文の後にあります。
# Requirements for Japanese Digital Text Layout

This Readme is a working document. We will update it along with the progress of the project. The English part of this document is in progress and incomplete.

## The motivation
Like manuscript and printed text, printed text and digital text stands on fundamentally different technologies. One fundamental difference is when/where the layout is finalised. With printing, the sender of the text fixes the layout, typically after manual inspections, and the sender distributes the single static image to all the receivers. With digital text, the layout is not resolved until the last minute. Many different images are generated automatically depending on the device environment and their preferences on the receiver's device. Such differences give digital text unique limitations and possibilities intrinsically distinct from printed text.

For this reason, we believe there are benefits to producing a document dedicated to digital text. At the meeting held on Oct. 2021, the JLreq Task Force members agreed to develop such a document as something that succeeds the existing JLreq that describes text layout on print. The tentative name is JLreq-d.

Because the digital text has a shorter history and is evolving, there will be areas to which we do not have a definite answer, and there will be issues with open questions. Still, we believe it is worth collecting practices we know so far and adding our thoughts to them. After the first version's completion, it needs to be updated periodically because the area is still in progress.

Another motivation for a new document is better support for software development. JLreq was almost revolutionary by describing the world of the high-quality Japanese text layout in English for the first time. Still, those who wish to implement Japanese layout software based on the JLreq face a few issues:
* The way JLreq is written is primarily generic and independent of particular technologies.
* The layout system evolved within a local market. As a result, it has a gap between internationalised systems.
* Some features are complex, but how you can simplify them or take a phased approach is not evident.
* It describes many features, but priorities between them are not evident. Similarly, when there are multiple ways to do one thing, it is not clear how one can choose one against another.
* Some areas are not covered well, e.g. fonts.

So, it still has a large gap that software engineers have to fill, sometimes by consulting with an expert in Japanese text layout, sometimes with never-ending discussions, and sometimes with guesswork. Such gap costs and slows development, sometimes makes people give up. We want to solve it by addressing the abovementioned issues. We expect it leads to better and more consistent implementations faster.

The last motivation is accessibility. Accessibility is becoming increasingly important, even for ordinary software and digital content. One unique advantage of digital text is the flexibility of the final image. Users can adjust it to their personal needs. The new document will explain things that creators of software and content need to consider to improve accessibility. It will treat accessibility as something ordinary that everyone has to know.

## The target audience
- Software Developers
- Content authors

## The target applications
- Simple text without or only basic styles such as mail and notes
- Web pages
- Word processor applications with pages
- E-books which has a structure as a book
- Web pages and text books with improved accessibility

### These are not the target
- Page layout and other applications who's purpose is to generate printed materials. JLreq covers them
- Graphic design and advitisement however the document would cover the basics

## The approach
…

…

…

# 日本語デジタルテキスト組版の要件
これは「生きている文書」であり、内容がプロジェクトの進行につれて変化する可能性があります。

## モティベーション
ちょうど手書きによる書写と印刷のように、印刷とWebに代表されるデジタルテキストでは、技術的な成り立ちが根底から異なっている。一つの根本的な違いは誰が組版を決定するかにある。印刷においては送り手が、しばしばプロによる校正ののち組版を決定し、単一のイメージに固定したものを受け手に配布する。デジタルテキストにおいては組版は送り手の元で完成せず、受け手の元で、デバイスの特性や受け手の好みに従って無数の異なるイメージが生成される。このような違いが印刷と本質的に異なる制約条件と可能性を生み出す[^note]。
[^note]: 詳細は 2019/03/31 Keiko Univ. APL 報告の木田の文章参照（ここにチェックインしておく？）。

このため、印刷のためではない、デジタルネイティブな組版について記述した文書を開発することは有用であると考える。デジタルテキストにフォーカスした要件文章を JLReq の先にあるものとして開発することの合意が JLReq TF で行われた（2021/10）。とりあえずの略称を JLreq-d とする。

デジタルデバイス上の組版は進化しつつある技術なので、はっきりとした答えがなかったり、未だ答えのない問題もあるだろう。それでも、現在までの経験や考察によりわかっていること、また明らかになった課題などを、一旦ここでまとめておくことに意味があると考える。また、現状に追い越されないように、一旦の完成後も将来のチームによって継続的なアップデートが必要になろう。

新しいドキュメントを作るもう一つのモティベーションは、開発支援である。JLreq は高品質な日本語組版を英語で記述した初めてのドキュメントであり、大きなインパクトをソフトウェア開発にもたらした。しかし、JLreq を読み下してソフトウェアに落とし込もうとすると、いくつかの障害に突き当たる。
- 多くの部分が技術独立に書かれている。
- 国内市場で培われてきた方法の記述であり、国際化された環境とのギャップがある。
- ルビ含めいくつかの組版は高度で複雑であるが、それを単純化する方法が明らかでない。
- 非常に多くの組版機能が説明されているがプライオリティが明らかではない。また、一つのことに複数の方法が説明されているときに、どの方法を取るべきかの判断の基準がない。
- 十分カバーされていないエリアがある。例：フォント

このため、ソフトウェアを開発しようとすると複雑な解釈が必要となり、日本語のエキスパートに相談したり、終わらない議論に巻き込まれたり、単に想像で実装を行ったりすることになる。それによって開発費が増大し、開発は遅れ、場合によっては実装を断念することになる。この問題を解決することで、より早期に、より多くの、またよりベンダ間で統一の取れた実装が得られることを期待する。

三つ目のモティベーションはアクセシビリティである。アクセシビリティは通常のソフトウェアやコンテントにとってもますます重要になりつつある。デジタルテキストの一つの特質は、ユーザーの必要や好みに応じて柔軟に最終イメージを作ることができることである。JLreq-d はアクセシビリティを誰もが理解しているべき通常のこととして扱う。ソフトウェアやコンテントをよりアクセシブルにするために考慮すべき点などを示すことで、より多くの人にとって使いやすい環境が達成されることを期待する。

## 対象読者
- ソフトウェア開発者
- コンテンツ制作者

## 対象とするアプリケーション
- メールやメモなど、組版指定のない、もしくは簡単なスタイルのみが使われる日常のテキスト
- Web ページ
- ワードプロセッサー文書（ページがある）
- 電子書籍（書籍としての構成を持つ）
- アクセシビリティの重要なWebページや教科書

#### これらは対象外とする
- 印刷のためのページレイアウトアプリケーション。これらはJLReqが対応する
- グラフィックデザインや広告。基本的な事柄はサポートするが

## アプローチ
### 書き方の方針
- 考え方を示す：デジタル技術の進化は早く、その上に成り立つデジタルテキストも従来より早い速度で変化してゆくと考えられる。ゆえ、組版の一つの方法をはっきりと示しつつも権威的にならず、同時に他の方法、その機能を考える際に重要なこと、答えのない課題などを提示することによって、判断のベースにし、また将来の進化を促す inspiring な内容にする。
- 基本的機能からより高度な機能へ内容を配列する：入口を低くする

### デジタルにおける新しい要素
- リフローアーキテクチャ。無数の組版が読み手の手元で生成されるアーキテクチャ
- 冊子形態が持つ意味の喪失
- 検索可能性
- ラグ組や空白行で区切られる欧文スタイルのパラグラフ
- ベースラインなど欧文ベースのエンジン上での振る舞い
- プロポーショナルな要素を多く含むテキスト、またプロポーショナルな和文書体の扱い
- リンクによるナビゲーションや注の機能など、デジタルテキストならではの優れた機能の利用
- より良いアクセシビリティの可能性
- 多様なサイズの画面。モバイルデバイスに代表される小さな画面

### 国際化ソフトウェア環境との親和性を高める方法
#### 多言語の中の日本語として記述
- 従来の JLReq は日本語に閉じた環境を扱っている。その意味で JLReq は JIS 文字規格に似ている。JLreq-d では Unicode のように国際化ソフトウェア環境の中の一つの言語としての日本語を扱う。
- その前提で、外国語、数式など日本語組版の中で規定する必要のないものは対象外。界面の振る舞いだけを定義する
#### 技術の扱いの方針
- 現在進行形の技術の中での組版なので、技術の前提なしに議論することは不可能である。同時に、技術の詳細からは中立に記述することによって、寿命の長い記述方法になることを期待する。
- ドキュメントでどの技術を前提としているかを明確化する。確立され、今後も使われると思われる基礎的な技術：Unicode、ウェブ技術、高機能フォント。
- 必要な組版機能に対して規格に不足があれば、その不足を洗い出して指摘する。規格化や実装が前に進んでいない機能を分析する。それらが前に進むことを支援できるように整理を行う。

#### 実装支援
- シンプル化、プライオリティ付け、デフォルトの方法の提案などにより規格化コスト・実装コストを下げる
- 日本語や日本語組版の概念を知らない技術者の理解のため、基本を書く
- 組版指定がなくても自動的に動くべき機能、言い換えるとプレーンテキストでも動くべき機能と、ルビのようにマークアップなどでの指定が必要な機能が見分けられるように書く
- 複数の方法がある場合、それが実装者の選択であるべきか、エンドユーザーの選択であるべきかを見分ける。印刷ではそれらを組版を行うものが決めていた

## 目次案
このレポジトリのGitHub wiki内の[目次案](https://github.com/w3c/jlreq-d/wiki/jlreq-d-ToC-draft)を参照ください。

See [draft Table of Content](https://github.com/w3c/jlreq-d/wiki/jlreq-d-ToC-draft) at GitHub wiki of this repository.
