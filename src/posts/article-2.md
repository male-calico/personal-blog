---
layout: article.njk
title: "個人ブログの構成について"
date: 2026-09-06
category: "BLOG"
tags: posts
image: "/images/featured-1.jpg"
---

- personal-blog/
    - src/
        - index.md
        - about.md
        - posts/  
            - article-1.md
            - article-2.md
            - article-3.md
        - css/
            - style.css
        - images/
            - article-1/
            - article-2/
    - _site/ （11tyが自動生成）
    - eleventy.config.js
    - package.json
    - package-lock.json
    - node_modules/

#### 役割
- src/：自分で作成するWebコンテンツ全般
- index.md：トップページ
- about.md：プロフィールなどの固定ページ
- posts/：ブログ記事のMarkdown
- css/：CSSファイル
- images/：ブログで使用する画像
- _site/：11tyが自動生成する完成品
- eleventy.config.js：11tyの設定
- package.json：プロジェクトの設定・使用パッケージ
- package-lock.json：パッケージの正確なバージョンを記録
- node_modules/：インストールされたNode.jsパッケージ

特に重要なのは、src と _site を明確に分けることです。

