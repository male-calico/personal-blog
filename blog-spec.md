# 個人ブログ仕様

## 目的

個人ブログとして、日々考えたことや興味のあることを記録・公開する。

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
- `src/_includes/`：Nunjucksテンプレート
- `_site/`：Eleventyが生成するファイル

## 現在の構成

- `src/index.md`：トップページ
- `src/_includes/layout.njk`：共通HTMLレイアウト
- `src/css/style.css`：基本CSS
- `eleventy.config.js`：Eleventyの設定

## デザイン方針

- 一般的なブログの構成を基本とする
- シンプルで洗練されたデザインを目指す
- トップページは「Featured Articles」と「Latest Articles」を組み合わせる
- 注目記事は大きく表示する
- その他の記事はカード形式で一覧表示する
- 画像を積極的に使用する
- 白背景と黒文字を基本とし、装飾は控えめにする
- 枠線や区切り線を使用して情報を整理する

## URL設計

- 今後決定

## 今後検討すること

- ブログ全体のデザイン
- 記事ページのデザイン
- レスポンシブ対応
- ナビゲーション
- カテゴリ・タグ
- GitHubへの公開