---
layout: article.njk
title: "個人ブログ制作 - 環境構築過程"
date: 2026-09-04
category: "BLOG"
tags: posts
image: "/images/featured-2.jpg"
---

まともにコードも書いたことがないプログラミング初心者が、AIと壁打ちしながら個人ブログ制作のための環境設定をしてみました。"Markdown → 11ty → HTML → GitHub Pages" を想定。

各コマンドや単語の説明は最下部に記載。
```
# はコメント。忘れないようメモメモ。
コマンド
```


### 1. Homebrew 6.0.21 導入

```bash
# Homebrewをインストール
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


### 2. nvm 0.40.7 導入

```bash
# nvmをインストール
brew install nvm
```


### 3. nvm 初期設定
```bash
# nvmの作業ディレクトリを作成
mkdir ~/.nvm
```

```bash
# nvmコマンドを自動で有効化

# NVM_DIRの環境変数設定を~/.zshrcに追加
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc

# ターミナル起動時にNVMを読み込む設定を~/.zshrcに追加
echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
```


### 4. Node.js 24.20.0 (LTS), (npm v11.19.0) 導入

```bash
# LTS版Node.js インストール
nvm install --lts
```


### 5. ブログ制作の設定を管理

```bash
# ブログ用フォルダを作成
mkdir ~/Developer
mkdir ~/Developer/personal-blog
```

```bash
# ブログ用フォルダへ移動
cd ~/Developer/personal-blog

# デフォルトの値でpackage.jsonを作成
npm init -y
```


### 6. 11ty 3.1.6 導入 (ローカルインストール)

```bash
# 11tyをインストール
npm install --save-dev @11ty/eleventy
```


### 7. ブログ制作用のファイル作成と設定

```bash
# Markdownファイル保存場所を作成
mkdir src

# Markdownファイルを作成
touch src/index.md
```

```bash
# 11ty設定ファイルを作成
touch eleventy.config.js

# (eleventy.config.js)に設定内容を記述
module.exports = function (eleventyConfig) {
    return {
        dir: {
            input: "src",
            output: "_site"
        }
    };
};
```


### 8. 11ty動作確認
```bash
# 11tyでHTMLを生成
npx @11ty/eleventy
```

---
##### 一言メモ: 
```
- brew         : Homebrewを操作するためのコマンド
- cd           : 作業する場所を移動するためのコマンド
- echo         : 文字列や変数の値を出力・表示するためのコマンド
- mkdir        : フォルダを作成するためのコマンド
- npx          : パッケージを実行するためのコマンド
- touch        : 空のファイルを作成するためのコマンド

- Homebrew     : パッケージ管理システム
- Node.js      : JavaScriptをPC上で実行するための実行環境
- npm          : Node.jsのパッケージ管理ツール
- nvm          : Node.jsのバージョン管理ツール
- 11ty         : MarkdownやHTMLから静的サイトを生成するためのツール

- ~/Developer  : 開発用フォルダ
- personal-blog: ブログ制作用フォルダ
- package.json : Node.jsプロジェクトの設定ファイル
- src          : Markdownを読み込む場所
- _site        : HTMLを出力する場所
```