---
author: Katsuhiro Ogata
lang: ja
title: あの電子書籍リーダーの表示性能が知りたい!　 電子書籍『EPUBリーダー表示テスト』活用術
---

# 
  <span style="font-size:2.5em; font-weight: bold;">あの電子書籍リーダーの<br/>表示性能が知りたい!</span><br/>
  <span style="font-size: 1.5em; font-weight: bold;"> 電子書籍『EPUBリーダー表示テスト』活用術</span>


<p style="position: absolute; bottom: 0; left: 0; width: 100%;">小形克宏（次世代パブリッシング研究会）<br/>
2025年11月25日<br/>
Advanced Publishing Lab.（APL）＋日本電子出版協会（JEPA）共催セミナー<br/></p>

# 自己紹介

- 小形克宏（おがた　かつひろ）
- 一般社団法人ビブリオスタイル理事
- CSS組版でワンソースから印刷用とEPUBが出力できるライブラリ[「Vivliostyle」](https://vivliostyle.org/ja/)の開発団体
- 代表理事である村上真雄も、CSSテストの制作を担当した
- EPUBリーダーテストの実施者として利益が相反するのは確か
- しかし、GitHubリポジトリやテスト結果を公開することで、客観性の担保に努めた

#   次世代パブリッシング研究会とは？

- 出版・印刷の未来を考える業界内勉強会
- 2000年代、「XMLコンソーシアム／クロスメディアパブリッシング部会」として創設
- 2010年4月、日本印刷技術協会（JAGAT）を拠点とする「XMLパブリッシング（準）研究会」に改名
- 2022年、「JAGAT次世代パブリッシング研究会」に改称
- 2025年4月、現在の名称になる
- 活動内容はメンバー全員で「調べてみる系」と「作ってみる系」
- 一緒に活動する人、大歓迎❗→[Discord招待リンク](https://discord.gg/aXQ7BQSW)

# これまでの経緯❶

- 『EPUBリーダー表示テスト報告書（2023年度）』のはじまり
  - （以下、2003年調査）
- 2022年12月定例会にてテストの実施が決定
  - 2010年の「電子書籍元年」から10年以上がすぎ、ここで改めてEPUBリーダーが今どうなっているのか振り返る
  - 同じ仕様に基づいているにもかかわらず、意外にEPUBリーダーによって挙動が異なる
  - 皆で現状の可視化を図るのは、会の活動として面白いのでは


# これまでの経緯❷

- 2003年調査でわかったこと
    - [EPUBリーダー表示テスト報告書（2023年度）](https://github.com/jagat-xpub/viewer-test-2023)
    - EPUBリーダーとレイアウトエンジンは以下の2つに二極分化
        - **モダンブラウザー系**
          - ブラウザのエンジンを流用、最近のCSS仕様をサポート
          -  Apple「ブック」、楽天Koboのモバイルアプリ
        - **独自エンジン系**
          - 独自開発または古いエンジンを搭載し、CSSのサポートは限定的
          - Amazon「Kindle」やhonto、Kinoppy、楽天KoboのPCアプリ・専用端末等
    
    
 # これまでの経緯❸   
    
- 日本の電子書店リーダーの多くは独自エンジン系
- では、ブラウザのレイアウトエンジンを使わないメリット・デメリットは？
  - **メリット**
    - 自分達の過去の実装との互換性が確保できる
  - **デメリット**
    - ゼロからCSSを実装しなければならないので、時間と労力がかかる（一度作ったら抜本的アップデートがしづらい）
    - その結果、進化を続けるEPUB仕様と乖離してしまう
    - アクセシビリティに対応できない
      - EPUBに限らず、W3Cはアクセシビリティ対応を主な活動目標とする
      - 新しい技術を続々と仕様化している


# これまでの経緯❹

- JEPAセミナーに登壇（2024年4月24日）
  - [各社のEPUBリーダーは、現行CSS仕様やアクセシビリティをどれだけサポートしているのか？〈日本電子出版協会（2024年4月24日）〉](https://www.jepa.or.jp/sem/20240424/)
- ところが反響はたった2つ……
  1. [週刊出版ニュースまとめ＆コラム #617](https://hon.jp/news/1.0/0/47244#EPUBCSS2024424)
  2. ポット出版、沢辺社長から出版のお誘いが！


# これまでの経緯❺

- **［確認］**2023年調査の反省点（今回の出版の原点）
    - ⓵電子書店は出版社が作ったEPUBをそのまま売る訳ではない
        - テストファイルをサイドロードでテストするのには限界あり
        - 本当のテスト結果は、実際にテストファイルを販売しない限り分からない
        - **→では、実際に電子書店に流通させてみよう！**
    - ⓶テスト結果を見ただけでCSS仕様通りか否か判断できない
        - テスト結果を見ただけでは、多くの人はそれがなにを意味するか分からない
        - **→正しい表示のスクリーンショットを紙で出版しよう！**

# 『EPUBリーダー表示テスト』の発刊

<figure class="float-right-img">
  <img src="images/fig-1.png" alt="EPUBリーダー表示テスト" width="100%">
</figure>

- 意図や経緯については『EPUBリーダー表示テスト正解集』[概要ページ（版元ドットコム）](https://www.hanmoto.com/bd/isbn/9784866420301)参照
- 多くの電子書店（例外は後述）にて、110円にて発売中
  - [Amazon](https://amzn.asia/d/eYbp6nn)
  - [BOOK☆WALKER](https://bookwalker.jp/deb9ed146b-7a31-4818-bfbf-9393d56adb31/)
  - [Kinoppy](https://www.kinokuniya.co.jp/kinoppystore/detail.php?itemId=ID-EK-2210961100)
  - [Googleブックス](https://play.google.com/store/books/details?pcampaignid=books_read_action&id=9Fl_EQAAQBAJ)
  - などなど
- [ソースコードはGitHubリポジトリで公開中](https://github.com/jagat-xpub/epub-css-test/tree/main/epub-exp/99_epubtestmerge_v0)
- （デモ）

# 『EPUBリーダー表示テスト正解集』の発刊

<figure class="float-right-img">
  <img src="images/fig-2.png" alt="EPUBリーダー表示テスト" width="95%">
</figure>

- テスト結果の正しい表示（正解）スクリーンショットを1冊にまとめたもの
- [紙の書籍](https://amzn.asia/d/2m9RD9r)、及び[固定型EPUB](https://amzn.asia/d/eYbp6nn)で出版
- （デモ）

# 『EPUBリーダー表示テスト』を<br/>電子取次に納品した結果

- 結合文字によるリジェクト
  - BookLive!（ἀ <U+1F00>　他）
  - 楽天kobo
- SVG画像の非サポートによるリジェクト
  - コミックシーモア
- **これも実際に販売しなければ分からなかったこと**

# 電子書籍リーダー表示テスト（2025）の実施❶


- テストを公開し、一人でも多くの人にテストへの参加を呼びかけることに
  - [①電子書籍リーダー表示テスト（2025）](https://forms.gle/C6yzzC5ybs8fjbWx6)
    - CSS仕様適合性テスト（156問／村上）
  - [②電子書籍リーダー表示テスト（2025）](https://forms.gle/Pbdh7PLrPh238mgd7)
    - その他のEPUBリーダー表示テスト（16問／田嶋）
  - [③電子書籍リーダー表示テスト（2025）](https://forms.gle/YbzHYeAsuNJW7wdUA)
    - EPUB内文字、画像、背景表示テスト（95問／仁科）
  - [④電子書籍リーダー表示テスト（2025）](https://forms.gle/H6cXEwAbYR2PosWG6)
    - 追加テスト（25問／田嶋）


  # 電子書籍リーダー表示テスト（2025）の実施❷

- 応募資格：『EPUBリーダー表示テスト』（次世代パブリッシング研究会、ポット出版、2025年、110円）を**実際に購入した上で**、正確に、そして誠実に回答してくださる方なら、**どなたでも応募できます（ニックネーム可）**。なお、明らかにイタズラあるいは妨害と認められる回答は主催者が削除することを、あらかじめご了承ください。
- 第1回期限：2025年3月31日

  # 電子書籍リーダー表示テスト（2025）の実施❸

- テストの手順
  1. テスト対象の電子書店で前掲『EPUBリーダー表示テスト』を購入
  2. 当該電子書籍を表示させる
  3. 表示されたテストの結果をフォームに記入して送信する
- 参考：テスト内容を解説した書籍、『EPUBリーダー表示テスト正解集』（次世代パブリッシング研究会、2025年、ポット出版、2,300円）を参照するとテストがやり易いでしょう

# このテストで、こんなことが分かる

- 最後に、[①電子書籍リーダー表示テスト（2025）](https://forms.gle/C6yzzC5ybs8fjbWx6)（**CSS仕様適合性テスト**）の具体的な内容について説明
- 今回公開するテストに先行しておこなった、プレビューテストの結果報告
- テスト対象とした電子書店は、我が国で最もシェアが高いKindleストア
- テストに使ったデバイスは、iPhone、Android、Windows、Kindle（第11世代）、Kindle専用端末の5種
  - 時間がなく、Macではテストができなかったことに注意
- ここで報告するテストは①だけで、②④はこの後で発表する田嶋氏、③は仁科氏が説明
- 一人でも多くの人に参加してもらうために、「例えばこんなことが分かる」を説明したい

# Kindle for PC（Windows）で<br/>縦書きができてない？❶

![※この赤い「NG」はKindle for PC（Windows用）](images/fig-3-0.png){width=100%}

# Kindle for PC（Windows）で<br/>縦書きができてない？❷

<div class="side-by-side">
<img src="images/fig-3.png" alt="CSS Writing Modes Level 3 writing-mode プロパティ" width="40%" />
<img src="images/fig-3-2.png" alt="和欧間自動アキ指定（タテ）" width="40%" />
</div>

- **左：**Kindle for PCでの①電子書籍リーダー表示テスト（2025）のテスト結果／**右：**同じく②におけるテスト結果

# 縦書きがNG、OKだった理由

- 縦書きが効かなかった箇所のスタイル（左）と、効いた箇所のスタイル（右）

<div class="side-by-side">
<img src="images/fig-3-3.png" alt="縦書きが効かなかった箇所のスタイル"/>
<img src="images/fig-3-4.png" alt="縦書きが効いた箇所のスタイル" />
</div>

- 左は現在の正しい記法
- 右は電書協ガイドのベンダープレフィックス（実装者固有の接頭辞）の記法
  - 新版でも電書協ガイドはベンダープレフィックスは有効
  - EPUB 3.3（および各種Web標準）では、非推奨（Deprecated）

# アクセシビリティからみたKindle

- 現在の電子書籍リーダーにとって「喫緊の課題」がアクセシビリティ対応のはず
- そこで今回のCSS仕様適合性テストで、5端末全てがNGだったCSSルール（全70）の中から、[“EPUB Accessibility 1.1”](https://www.w3.org/TR/epub-a11y-11/) 及び [“Web Content Accessibility Guidelines (WCAG) 2.2”](https://waic.jp/translations/WCAG22/) への対応のために、とくに必要なルールを4つ紹介します


# `unicode-range` 記述子と`orphans` / `widows` プロパティの未サポート


<figure style="float: left; width: 56%; margin: 0;">
  <img src="images/fig-4.png" alt="" style="width: 100%;">
  <figcaption>CSS Fonts Level 3 unicode-range 記述子</figcaption>
</figure>

<figure style="float: right; width: 42%; margin: 0;">
  <img src="images/fig-5.png" alt="" style="width: 100%;">
  <figcaption>CSS Fragmentation Module Level 3 orphans, widows プロパティ</figcaption>
</figure>

<div style="clear: both;"></div>

### `unicode-range` , `orphans` / `widows`とアクセシビリティ

| CSS要素 | 関連するWCAG達成基準 | EPUB A11Y 1.1における役割 |
| :--- | :--- | :--- |
| **1. `unicode-range` 記述子** | 1.1.1 (非テキストコンテンツ) | **【情報保障】** コンテンツ内の特殊な文字が欠落せず表示されることを保証し、**文字化けを防ぐ**。 |
| **2. `orphans` / `widows` プロパティ** | 1.4.8 (視覚的提示) | **【認知負荷の軽減】** 段落の不自然な分断を防ぐことで、読者の視覚的な追従負担を減らし、**可読性を高める**。 |


# 論理プロパティとCSS変数の未サポート

<div class="side-by-side">
<img src="images/fig-6.png" alt="CSS Logical Properties and Values Level 1 論理プロパティ padding-block" width="50%" />
<img src="images/fig-7.png" alt="CSS Fragmentation Module Level 3 orphans, widows プロパティ" width="50%" />
</div>



### 論理プロパティとCSS変数とアクセシビリティ

| CSS要素 | 関連するWCAG達成基準 | EPUB A11Y 1.1における役割 |
| :--- | :--- | :--- |
| **3. 論理プロパティ** (例: `padding-block`) | 1.3.1 (情報及び関係性) | **【構造的適応性】** 物理的指定から論理的指定へ移行することで、**縦書き・横書きのどちらでも一貫した構造**と余白を維持する。 |
| **4. CSS変数** (Custom Properties) | 1.4.3 (コントラスト) / 1.4.8 (視覚的提示) | **【テーマの柔軟性】** ハイコントラストやフォントサイズ調整など、**ユーザーによるテーマの一括切り替え**を容易にし、ユーザースタイルを尊重する。 |


# おしまい。田嶋さんの報告につづきます


