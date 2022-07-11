[日本語](#日本語デジタルテキスト組版の要件)は英文の後にあります。
# Requirements for Japanese Digital Text Layout

This Readme is a working document. We will update it along with the progress of the project. The English part of this document is in progress and incomplete.

The [Japanese Language Enablement](https://w3c.github.io/jlreq/home) home page provides links and information about related work and the organization of the group. This page focuses specifically on information related to the document Requirements for Japanese Digital Text Layout.

## The motivation
Like manuscript and printed text, printed text and digital text stand on fundamentally different technologies. One fundamental difference is when/where the layout is finalised. With printing, the sender of the text fixes the layout, typically after manual inspections, and the sender distributes the single static image to all the receivers. With digital text, the layout is not resolved until the last minute. Many different images are generated automatically depending on the device environment and their preferences on the receiver's device. Such differences give digital text unique limitations and possibilities that are intrinsically distinct from printed text.

For this reason, we believe that there are benefits to producing a document dedicated to digital text. At the meeting held in Oct. 2021 the JLreq Task Force members agreed to develop such a document as a successor to the existing JLreq, which describes text layout in print. The tentative name is JLreq-d.

Because digital text has a shorter history and is evolving, there will be areas to which we do not have a definitive answer, and there will be issues with open questions. Still, we believe it is worth collecting practices we know of so far, and adding our thoughts to them. After the first version is complete it will need to be updated periodically because the technology is still in progress.

Another motivation for a new document is better support for software development. JLreq is almost revolutionary in that it describes the world of high-quality Japanese text layout in English for the first time. Still, those who wish to implement Japanese layout software based on JLreq face a few issues:
* The way JLreq is written is primarily generic and independent of particular technologies.
* The layout system evolved within a local market. As a result, there is a gap between it and internationalised systems.
* Some features are complex, but how to simplify them or take a phased approach is not evident.
* It describes many features, but priorities between them are not evident. Similarly, when there are multiple ways to do one thing, it is not clear how one can choose one against another.
* Some areas are not covered well, e.g. fonts.

So, there is still a large gap that software engineers to fill, sometimes by consulting with an expert in Japanese text layout, sometimes with never-ending discussions, and sometimes with guesswork. Such gaps cost and slow development, sometimes making people give up. We want to solve those issues by addressing the abovementioned items. We expect it to lead to better and more consistent implementations, and to do so faster.

The last motivation is accessibility. Accessibility is becoming increasingly important, even for ordinary software and digital content. One unique advantage of digital text is the flexibility of the final image. Users can adjust it to their personal needs. The new document will explain things that creators of software and content need to consider to improve accessibility. It will treat accessibility as something basic that everyone has to know.

## Target audience
- Software Developers
- Content authors

## Target applications
- Simple text without styling or only basic styles, such as mail and notes
- Web pages
- Word processor applications with pages
- E-books, which are structured as a book
- Web pages and text books, with improved accessibility

### Non targets
- Imitating the look of the pinted books. JLreq covers them
- Page layout and other applications who's purpose is to generate printed materials. JLreq covers them
- Graphic design and advertisements, however the document would cover the basics

## Approach
### Editorial policy
- Where possible and appropriate, the document will try providing reasons behind particular layout rules to help readers to understand the feature better. When there are multiple possible ways or values or no clear answer, it will also try providing background information to help readers make their own decisions. We also expect they will facilitate discussions and progress.
- The document will arrange sections from basic features that everybody has to understand to high-level or area-specific features.
…

…

…
## Draft TOC
See [draft Table of Content](https://github.com/w3c/jlreq-d/wiki/jlreq-d-ToC-draft) at GitHub wiki of this repository.

#
# 日本語デジタルテキスト組版の要件
これは「生きている文書」であり、内容がプロジェクトの進行につれて変化する可能性があります。

## モティベーション
ちょうど手書きによる書写と印刷のように、印刷とWebに代表されるデジタルテキストでは、技術的な成り立ちが根底から異なっている。一つの根本的な違いは誰が組版を決定するかにある。印刷においては送り手が、しばしばプロによる校正ののち組版を決定し、単一のイメージに固定したものを受け手に配布する。デジタルテキストにおいては組版は送り手の元で完成せず、受け手の元で、デバイスの特性や受け手の好みに従って無数の異なるイメージが生成される。このような違いが印刷と本質的に異なる制約条件と可能性を生み出す[^note]。
[^note]: 詳細は 2019/03/31 Keiko Univ. APL 報告の木田の文章参照（ここにチェックインしておく？）。

このため、印刷のためではない、デジタルネイティブな組版について記述した文書を開発することは有用であると考える。デジタルテキストにフォーカスした要件文章を JLReq の先にあるものとして開発することの合意が JLReq TF で行われた（2021/10）。とりあえずの略称を JLreq-d とする。

デジタルデバイス上の組版は進化しつつある技術なので、はっきりとした答えがなかったり、未だ答えのない問題もあるだろう。それでも、現在までの経験や考察によりわかっていること、また明らかになった課題などを、一旦ここでまとめておくことに意味があると考える。また、現状に追い越されないように、一旦の完成後も将来のチームによって継続的なアップデートが必要になろう。

新しいドキュメントを作るもう一つのモティベーションは、開発支援である。JLreq は高品質な日本語組版を英語で記述した初めてのドキュメントであり、大きなインパクトをソフトウェア開発にもたらした。しかし、JLreq を読み下してソフトウェアに落とし込もうとすると、いくつかの障害に突き当たる。
- 多くの部分が技術独立に書かれており、技術への翻訳に時間がかかる。
- 国内市場で培われてきた方法の記述であり、国際化された環境とのギャップがある。
- ルビ含めいくつかの組版は高度で複雑であるが、比較的簡単なアプリケーションのためや、段階的実装のためにそれを単純化する方法が明らかでない。
- 多くの組版機能が説明されているがプライオリティが明らかではない。また、一つのことに複数の方法が説明されているときに、どの方法を取るべきかの判断の基準がない。
- 十分カバーされていないエリアがある。例：フォント

このため、ソフトウェアを開発しようとすると複雑な解釈が必要となり、日本語のエキスパートに相談したり、終わらない議論に巻き込まれたり、単に想像で実装を行ったりすることになる。それによって開発費が増大したり、開発が遅れたり、場合によっては実装を断念する結果になってしまう場合もある。この問題を解決することで、より早期に、より多くの、またよりベンダ間で統一の取れた実装が得られることを期待する。

三つ目のモティベーションはアクセシビリティである。アクセシビリティは通常のソフトウェアやコンテントにとってもますます重要になりつつある。デジタルテキストの一つの特質は、ユーザーの必要や好みに応じて柔軟に最終イメージを作ることができることである。JLreq-d はアクセシビリティを誰もが理解しているべき通常のこととして扱う。ソフトウェアやコンテントをよりアクセシブルにするために考慮すべき点などを示すことで、より多くの人にとって使いやすい環境が達成されることを期待する。

## 対象読者
- ソフトウェア開発者
- コンテンツ制作者

## 対象とするアプリケーション
- メールやメモなど、組版指定のない、もしくは簡単なスタイルのみが使われる日常のテキスト
- Web ページ。リフロー、スクロール
- ワードプロセッサー文書。ページのあるもの
- 電子書籍。書籍としての構成を持つもの
- アクセシビリティの重要なWebページや教科書

#### 対象外
- 印刷された書籍の見かけを模倣すること。これはJLReqが対応する
- 印刷のためのページレイアウトアプリケーション。これらはJLReqが対応する
- グラフィックデザインや広告。基本的な事柄はサポートするが詳細は対象外

## アプローチ
### 編集方針
- 考え方を示す：組版機能に対し、なぜそのような方法になっているのか、その理由を可能な限り示すことでより良い理解を助ける。可能な方法や値が一つでない場合や、明確な答えがない場合には、その機能を考える際に重要な要素を示すことで、独自の判断を助ける。結果のみではなく理由を示すことで、議論と将来の進化を促すような内容にする。
- 誰もが理解すべき基本的機能から、高度なもしくは特定の分野のみで必要な機能へと内容を配列する

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
