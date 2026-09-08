---
layout: article.njk
title: "個人ブログ制作 - 環境構築過程"
date: 2026-09-04
category: "BLOG"
tags: posts
image: "/images/featured-2.jpg"
---

1. Homebrew 6.0.21 導入
    - "Homebrew インストールコマンド" を実行
        - /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
2. nvm 0.40.7 導入
    - "nvm インストールコマンド" を実行
        - brew install nvm
3. nvm 初期設定
    - "nvm用の作業ディレクトリ 作成コマンド" を実行
        - mkdir ~/.nvm  
        ※ nvmがインストールしたNode.jsを保存する場所
    - "nvmコマンドを自動有効化 するコマンド" を実行
        - echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
        - echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
        - echo '[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"' >> ~/.zshrc
4. Node.js 24.20.0 (LTS), npm v11.19.0 導入
    - "LTS版Node.js インストールコマンド" を実行
        - nvm install --lts
5. ブログ制作用下準備 1
    - "ブログ用フォルダ 作成コマンド" を実行
        - pwd
        - mkdir ~/Developer
        - mkdir ~/Developer/personal-blog
        - cd ~/Developer/personal-blog
    - "package.jsonファイル 作成コマンド" を実行
        - npm init -y
6. 11ty 3.1.6 導入 (ローカルインストール)
    - "11ty インストールコマンド" を実行
        - npm install --save-dev @11ty/eleventy
7. ブログ制作用下準備 2
    - "(.md) ファイル保存場所 作成コマンド" を実行
        - mkdir src
    - "(.md)ファイル 作成コマンド" を実行
        - touch src/index.md
    - "11ty 設定ファイル 作成コマンド" を実行
        - touch eleventy.config.js
    - "(eleventy.config.js)ファイル" に設定内容を記述
8. テスト
    - "11ty" を実行
        - npx @11ty/eleventy