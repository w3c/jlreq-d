[日本語](#日本語デジタルテキスト組版の要件)は英文の後にあります。
# Requirements for Japanese Digital Text Layout

This Readme is a working document. We will update it along with the progress of the project.

The [Japanese Language Enablement](https://w3c.github.io/jlreq/home) home page provides links and information about related work and the organization of the group. This page focuses specifically on information related to the document Requirements for Japanese Digital Text Layout.

## The motivation
Like manuscript and printed text, printed text and digital text stand on fundamentally different technologies. One fundamental difference is when/where the layout is finalised. With print, the sender of the text fixes the layout, typically after manual inspections, and the sender distributes the single static image to all the receivers. With digital text, the layout is not resolved until the last minute. Many different images are generated automatically depending on the device environment and their preferences on the receiver's device. Such differences give digital text unique limitations and possibilities that are intrinsically distinct from printed text.

For this reason, we believe that there are benefits to producing a document dedicated to digital text. At the meeting held in Oct. 2021 the JLreq Task Force members agreed to develop such a document as a successor to the existing JLreq, which describes text layout in print. The tentative name is JLreq-d.

Because digital text has a shorter history and is evolving, there will be areas to which we do not have definitive answers, and there will be areas with open questions. Still, we believe it is worth collecting practices we know of so far, and adding our thoughts to them. After the first version is complete it would need to be updated periodically because the technology is still in progress.

Another motivation for a new document is better support for software development. JLreq is almost revolutionary in that it describes the world of high-quality Japanese text layout in English for the first time. Still, those who wish to implement Japanese layout software based on JLreq face a few issues:
* The way JLreq is written is primarily generic and independent of particular technologies.
* The layout system evolved within a local market. As a result, there is a gap between it and internationalised systems.
* Some features are complex, but how to simplify them or take a phased approach is not evident.
* It describes many features, but priorities between them are not evident. Similarly, when there are multiple ways to do one thing, it is not clear how one can choose one against another.
* Some areas are not covered well, e.g. fonts.

So, there is still a large gap that software engineers to fill. They have to fill it by consulting with experts in Japanese text layout, sometimes with never-ending discussions, and sometimes with a guesswork. Such gaps cost and slow development, often making people give up. We want to solve it by addressing abovementioned issues. We expect it to lead to better and more consistent implementations, and to do so faster.

The last motivation is accessibility. Accessibility is becoming increasingly important, even for ordinary software and digital content. One unique advantage of digital text is the flexibility of the final image. Users can adjust it to their personal needs. The new document will explain things that creators of software and content need to consider to improve accessibility. It will treat accessibility as something basic that everyone has to know.

## Target audience
- Software Developers
- Content authors

Including those that are with limited knowledge in Japanese language.

## Target applications
As mentioned earlier, the layout of digital text has its unique limitations and possibilities that are dictinct from printed text. As the object of JLReq-d is to reflect them to the requirements, applications that aim to reproduce details of traditional line layout are out of scope. Please refer to the original JLReq for such a requirements.

These applications for example are out of the scope:
- Professional page layout applications or word processor applications that aim to reproduce details of traditional layout
- E-book applications that aim to reproduce the layout of printed books

JLReq-d targets these applications:
- Mail, notes or UI text: Simple text without a style or only basic styles. Typically without justification
- Web pages: reflow and scroll
- Word processor and presentation apps: which have a concept of a page
- E-books: which are structured as books

## Editorial policy
### Explain background information
- Where possible and appropriate, the document will try providing reasons behind layout rules in order to help readers to understand the feature better. When there are multiple possible ways or values or no clear answer, it will also try providing background information to help readers make their own decisions. We also expect they will facilitate discussions and future progress.

### Describe Japanese layout in internationalised software environment
- The original JLReq describes the Japanese line layout rules that have established and closed within the domestic market. JLReq-d will try to describe it as one of the language in an internationalised software environment. In a sense the difference is similar to the comparison between the JIS character standard and the Unicode.
- It will cover necssary basic knowledge of Japanese language for those who are not necesarily familiar with the language.
- It will cover technologies such as fonts that are necessary to implement Japanese language in an internationalized environment but are not covered well in the original JLReq.

### Handling of technologies
- It will choose a few basic and stable technologies and use them in the description to facilitate development. Will clearly document ones that are assumed. The current thinkinig is Unicode, HTML/CSS, and smart fonts like OpenType.
- It will try point out when we found shortcomings in the current standards or implementations to achieve necessary layout features. These parts will need periodical updates.

### Facilitating development
- It will try reducing the standardization and development cost by making the specification simpler where possible and appropriate, and by suggesting relative priorities and default values with reasonings.

### Content structure
- It will first describe basic knowledge and features that everyone needs to understand and implement, folloed by high level features and area specific features.

## Random list of new items, characteristics, or things that has to be considered in digital text
- It reflows. A large number of different layouts are generated at users' hand depending on their environment and preferences.
- The codex (vs scroll) format, the way pages are bound as book, loses most of its benefits on digital.
- It is searchable. It has to be searchable for, among other things, accessibility.
- How does Western style layout such as left justification and paragraphs separated by a linefeed fit?
- How Japanese characters should be placed and behave on Wetern style layout system using the baseline?
- How do we layout lines that has many proportional characters? Before print Japanese characters were also proportional and there are such fonts.
- There are a few different ways of adding notes to the text. Many of them are placed in or at the side of the line. Which one should we preserve and which can be replaced by new ways of adding notes in digital text?
- Digital for better accessibility.
- Has to support wide variety of screen sizes, from smartphones to a large screen. For example how line length and the cap between lines should be when the size changes?
- The dynamic behaviour of the text on UI has to be described. For example what should be highlighted when you select lines with ruby? What should be copied when it is copied?
- Some features should work automatically without the contents prividers' or the readers' additional instructions, i.e. something that has to work even on plane text. Some features require markup, e.g. ruby, by the contents prividers. Some features should be left to the readers' choice such as font size. There were no such distinctions in print. Probably we have to be concious of such distinctions in describing features.

## Draft TOC
See [draft Table of Content](https://github.com/w3c/jlreq-d/wiki/jlreq-d-ToC-draft) at GitHub wiki of this repository.

#
# 日本語デジタルテキスト組版の要件
これは「生きている文書」であり、内容がプロジェクトの進行につれて変化する可能性があります。

この JLreq-d レポジトリは日本語タスクフォースのプロジェクトの一つである、日本語デジタルテキストに特化した組版要件文書を開発するための場所です。「日本語組版の要件 (JLReq)」を含め、関連したプロジェクト、および日本語タスクフォースの構成、参加の仕方などの情報は[Japanese Language Enablement, 日本語組版要件](https://w3c.github.io/jlreq/home) のホームページにあります。

## モティベーション
ちょうど手書きによる書写と印刷のように、印刷とWebに代表されるデジタルテキストでは、技術的な成り立ちが根底から異なっている。一つの根本的な違いは誰が組版を決定するかにある。印刷においては送り手が、しばしばプロによる校正ののち組版を決定し、単一のイメージに固定したものを受け手に配布する。デジタルテキストにおいては組版は送り手の元で完成せず、受け手の元で、デバイスの特性や受け手の好みに従って無数の異なるイメージが生成される。このような違いが印刷と本質的に異なる制約条件と可能性を生み出す[^note]。
（木田：違いの具体例を加える）
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

必ずしも日本語に精通しない読者を含む。

## 対象アプリケーション
モティベーションの項で述べたように、デジタルテキストの組版は従来の印刷と異なる制約と可能性を持っている。それらを要件に反映するのがJLReq-dの目的であるから、印刷組版の詳細な再現が重要な応用は対象外となる。そのような応用に対してはJLReqが対応する。

例えば下記のような応用は対象外となる：
- 書籍など印刷紙面の作成を本来の目的とし、印刷組版の詳細な再現が重要な組版アプリケーションやワードプロセッサー
- 印刷された書籍の見掛けの再現が重要な電子書籍アプリケーション

JLReq-d は下のような応用を念頭に置く：
- メール、メモ、UIテキストなど：組版指定なしまたは簡単なスタイルのみのシンプルなテキスト。典型的に行頭揃え
- Web ページ：リフロー、スクロールするもの
- 電子文書の作成を目的としたワードプロセッサーやプレゼンテーションソフトなど：ページの概念のあるもの
- 電子書籍：書籍としての構成を持つが、印刷書籍の再現を目的としないもの

## 編集方針
### 考え方を示す
- 組版機能に対し、なぜそのような方法になっているのか、その理由を示すことでより良い理解を助ける。組版の方法や値が複数ある場合や、明確な答えがない場合には、その機能を考える際に重要な要素を示すことで独自の判断を助ける。結果のみではなく理由を示すことで、そこで示されている方法と異なった方法を試みることを可能にし、また議論と将来の進化を促すような内容にする。

### 国際化環境の中の日本語として記述
- 従来のJLReqは日本語に閉じた環境を扱っている。その意味でJLReqはJIS文字規格に似ている。JLreq-dではUnicodeのように国際化ソフトウェア環境の中の一つの言語としての日本語を扱う。その前提で、外国語、数式など、日本語組版の中で規定する必要のないものは対象外。界面の振る舞いのみを定義する。
- 日本語や日本語組版に必ずしも精通していない技術者の理解のため、基本から書く。
- フォントなど、JIS X 4051 や JLReq が詳しく扱っていないが、国際化環境の中に日本語組版を成り立たせるために必要な技術をカバーする。

### 技術の扱いの方針
- 実装を支援するために、確立され今後も使われると思われる基礎的な技術を前提として受け入れて記述する。これら前提として採用している技術はドキュメントする。現時点での想定は：Unicode、ウェブ技術、高機能フォント。
- 必要な組版機能に対して規格・実装に不足があれば、その不足を洗い出して指摘する。この部分は規格や実装の進みに合わせて頻繁なアップデートが必要であろう。

### 実装支援
- シンプル化、プライオリティ付け、デフォルトの方法の提案などにより規格化コスト・実装コストを下げる

### 項目の排列の方針
誰もが理解すべき基本的機能から、高度なもしくは特定の分野のみで必要な機能へと内容を配列する


## デジタルにおける新しい要素のランダムメモ
- リフローする。読み手の環境や好みによって無数の異なる組版が読み手の手元で生成される
- 冊子形態はデジタルにおいてその持つ意味の多くを喪失する。四角さはと背表紙は収納と検索のため。固定長でページに分け、それに番号を振ることはランダムアクセスのための手段。巻物、スクロールという古い形式が復活する
- デジタルテキストは検索できる。そしてデジタルテキストは検索できるべきである。テキストとして取り出せることは特にアクセシビリティに重要。
- ラグ組や空白行で区切られる欧文スタイルのパラグラフをどのように取り入れられるか？
- 同様に、ベースラインなど欧文の組版の仕組みの上で和文はどのように配置され、振る舞うべきか？
- プロポーショナルな要素を多く含むテキスト、またプロポーショナルな和文書体の扱いをどうするべきか？ 活字の現れる前は和文もプロポーショナルであった
- 和文組版にはいくつかの異なる注の機能がある。多くは行の中、または横に配置される。どれを残すべきか。リンクによるナビゲーションや注の機能など、デジタルテキストならではの優れた機能の利用をどう組み合わせるか
- デジタルテキストにはより良いアクセシビリティの可能性がある
- 多様なサイズの画面。モバイルデバイスに代表される小さな画面から大きな画面までをサポートする必要がある。例えば多様なサイズに対して行長と行間はどうあるべきか？
- UIにおける動的挙動を定義する必要がある。例えばルビが含まれたテキストを選択した場合、何がハイライトされるべきか？　コピーしたら何がコピーされるべきか？
- 組版指定がなくても自動的に動くべき機能、言い換えるとプレーンテキストでも動くべき機能、ルビのように作成者による指定が必要な機能、そしてフォントサイズのようにエンドユーザーの選択が可能であるべき機能などの区別がある。印刷ではそれら全てを組版を行うものが決め、固定していた。この点を意識して記述する必要がありそうだ。

## 目次案
このレポジトリのGitHub wiki内の[目次案](https://github.com/w3c/jlreq-d/wiki/jlreq-d-ToC-draft)を参照ください。
