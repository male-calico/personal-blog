---
layout: article.njk
title: "個人ブログ制作 - 環境構築過程"
date: 2026-09-04
category: "BLOG"
tags: posts
image: "/images/featured-2.jpg"
---

まともにコードも書いたことがないプログラミング初心者が、AIと壁打ちしながら個人ブログ制作のための環境構築をしてみました。各コマンドや単語の説明は最下部に記載。
```
# はコメントです。忘れないようメモメモ。
コマンド
```

---

1. Homebrew 6.0.21 導入
    - Macユーザー御用達アイテム
    - CLIを通じてコマンド指示を出し、ソフトなどのインストールなどができる
    ```bash
    # Homebrew インストールコマンド
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. nvm 0.40.7 導入
    - "nvm インストールコマンド" を実行
        ```bash
        brew install nvm
        ```
3. nvm 初期設定
    - "nvm用の作業ディレクトリ 作成コマンド" を実行
        - nvmがインストールしたNode.jsを保存する場所
        ```bash
        mkdir ~/.nvm
        ```
    - "nvmコマンドを自動有効化 するコマンド" を実行
        ```bash
        echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
        echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
        echo '[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"' >> ~/.zshrc
        ```
4. Node.js 24.20.0 (LTS), npm v11.19.0 導入
    - "LTS版Node.js インストールコマンド" を実行
        ```bash
        nvm install --lts
        ```
5. ブログ制作用下準備 1
    - "ブログ用フォルダ 作成コマンド" を実行
        ```bash
        pwd
        mkdir ~/Developer
        mkdir ~/Developer/personal-blog
        cd ~/Developer/personal-blog
        ```
    - "package.jsonファイル 作成コマンド" を実行
        ```bash
        npm init -y
        ```
6. 11ty 3.1.6 導入 (ローカルインストール)
    - "11ty インストールコマンド" を実行
        ```bash
        npm install --save-dev @11ty/eleventy
        ```
7. ブログ制作用下準備 2
    - "(.md) ファイル保存場所 作成コマンド" を実行
        ```bash
        mkdir src
        ```
    - "(.md)ファイル 作成コマンド" を実行
        ```bash
        touch src/index.md
        ```
    - "11ty 設定ファイル 作成コマンド" を実行
        ```bash
        touch eleventy.config.js
        ```
    - "(eleventy.config.js)ファイル" に設定内容を記述
        - input  = src       ← Markdownを読む場所
        - output = _site     ← HTMLを出力する場所
        ```bash
        module.exports = function (eleventyConfig) {
            return {
                dir: {
                    input: "src",
                    output: "_site"
                }
            };
        };
        ```
8. テスト
    - "11ty" を実行
        ```bash
        npx @11ty/eleventy
        ```

