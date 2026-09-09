# 個人ブログ仕様

## 目的

- 個人ブログとして、日々考えたことや興味のあることを記録・公開する。

## 技術構成

- Markdown：記事の執筆
- Eleventy (11ty)：MarkdownからHTMLへの変換
- Nunjucks：HTMLテンプレート
- CSS：デザイン
- Node.js：開発環境
- GitHub：公開・バージョン管理

## フォルダ構成

- `src/`：自分で編集するファイル
- `src/posts/`：記事
- `src/css/`：CSS
- `src/images/`：画像
- `src/_layouts/`：Nunjucksテンプレート
- `_site/`：Eleventyが生成するファイル

## 現在の構成

- `src/index.md`：トップページ
- `src/about.md`：プロフィールなどの固定ページ
- `src/_layouts/layout.njk`：共通HTMLレイアウト
- `src/_layouts/article.njk`：記事ページ用レイアウト
- `src/css/style.css`：基本CSS
- `eleventy.config.js`：Eleventyの設定

## デザイン方針

- 一般的なブログの構成を基本とする
- シンプルで洗練された、コンテンツ中心のデザインを目指す
- ダークな青灰色を基調とし、装飾は控えめにする
- トップページは「Selected Articles」と「Recent Articles」を組み合わせる
- Selected Articlesは注目記事を大きく表示する
- Recent Articlesはその他の記事をカード形式で一覧表示する
- 画像を積極的に使用する
- 枠線や区切り線を使用して情報を整理する
- システムフォントを使用し、外部Webフォントは使用しない

## 現在のカラーパレット

- 背景：`#414953`
- カード・画像領域：`#48515A`
- 本文：`#F0F2F1`
- 補助文字：`#B5BEC0`
- 境界線：`rgba(89, 99, 106, 0.5)`
- アクセント・リンク：`#8FB5A3`
- リンクホバー：`#A8C8B7`

## 現在のレイアウト

- 本体の最大幅：`1100px`
- 本体の左右余白：`30px`
- Selected Articles：メイン記事1件＋サイド記事2件
- Selected Articlesはレスポンシブ対応済み
- Selected Articlesのカード境界線は薄く表示する
- Recent Articles：記事を縦方向のリストとして表示する
- Recent Articlesのカード全体をリンク化する
- 記事タイトルは、メイン記事 `1.4rem`、サイド記事 `1.1rem` を基準とする
- スマートフォンでは記事タイトルを `1.8rem` に調整する

## ナビゲーション

- スマートフォン用ハンバーガーメニューを実装済み
- レスポンシブ表示に対応する

## 記事ページ

- 記事本文のコードはMarkdownから`<pre><code>`のコードブロックとして表示する
- 長いコードは横スクロールできるようにする
- Markdownの`---`による`<hr>`は薄い区切り線として表示する
- Markdownの`##`による`<h2>`には区切り線を表示する
- `<hr>`と`<h2>`の区切り線には `rgba(89, 99, 106, 0.5)` を使用する

## URL設計

- 今後決定する

## 今後検討すること

- ブログ全体のデザイン
- 記事ページのデザイン
- カテゴリ・タグ
- GitHubへの公開
