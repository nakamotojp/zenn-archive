---
title: 【超入門】古いPCが蘇る！ChromeOS Flexで子供のプログラミング環境を整える方法
tags: Windows10 Chromebook Scratch
author: nakamoto
slide: false
---
# 【超入門】古いPCが蘇る！ChromeOS Flexで子供のプログラミング環境を整える方法

---

古いPCを再活用したい…  
でも、Windows10はもうすぐ終わるし、Linuxは難しそう…。  
そんな時にぴったりなのが **ChromeOS Flex**。

Googleが提供する、**古いパソコンをChromebook化**できる軽量OSです。

本記事では以下の内容をわかりやすく解説します。

---

## ✅ この記事の内容

1. 💻 ChromeOS Flexのインストール方法  
2. 🧒 Scratchの使い方（Web版）  
3. 🧠 VSCODEとは？なぜ必要？  
4. 💾 VSCODEのインストール方法（Linux環境有効化）  
5. 🎮 Claude + VSCODEで小学生がゲームを作る流れ

---

## 💻 1. ChromeOS Flexのインストール方法

### 必要なもの

- 8GB以上のUSBメモリ（中身は消えます）
- Chromeブラウザが入ったPC（Windows or Mac）

### ステップ

1. [Chromebook リカバリ ユーティリティ](https://chrome.google.com/webstore/detail/chromebook-recovery-utility) をインストール  
2. 拡張機能を起動 → 「新しいメディアを作成」  
3. 製品名で「**Google ChromeOS Flex**」を選択  
4. USBに書き込む（約10分）  
5. インストールしたいPCにUSBを挿して起動 → Boot MenuでUSBを選択（F12, ESC, DeleteなどはPCにより異なる）  

> 🌱 お試し起動も可能（USBから起動）  
> 👍 気に入ったらインストールを選択

---

## 🧒 2. Scratchを利用する方法（Web版）

ChromeOS Flexでは基本的に**Webアプリで操作**します。

### Scratchの使い方

1. Chromeブラウザを起動  
2. [https://scratch.mit.edu](https://scratch.mit.edu) にアクセス  
3. アカウントを作成（任意）  
4. 「作る」ボタンからブロックプログラミングを開始！

> 🎨 子供向けの直感的なインターフェース  
> 🚀 Chromebookでもサクサク動作します

---

## 🧠 3. VSCODEとは？

Visual Studio Code（通称VSCode）は、**無料のプログラミング用エディタ**です。

| 機能             | 説明                                |
|------------------|-------------------------------------|
| 📝 高機能なコード補完 | タイピングをサポート                 |
| 🔌 拡張機能が豊富     | Python, HTML, ゲームエンジン等に対応 |
| 🌍 Chromebook対応     | Linux環境があれば動作可能            |

> 子供がPythonやHTML、JavaScriptを学ぶ上で最適なツールです。

---

## 💾 4. VSCODEのインストール方法（ChromeOS Flexで）

### まずLinux環境を有効化

1. 「設定」→「開発者」→「Linux 開発環境」→「オンにする」  
2. 数分でインストールが完了  
3. ターミナルが起動される（ここでVSCodeをインストール）

### VSCodeのインストール（ターミナルで入力）

```bash
sudo apt update
sudo apt install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code
```

> ✅ インストール完了後、「アプリケーション」メニューに「Visual Studio Code」が表示されるようになります！

---

## 🎮 5. Claude + VSCodeで小学生がゲームを作る流れ

### 🧠 Claudeとは？

ClaudeはAnthropic社が提供する**AIアシスタント**で、ChatGPTのように会話形式でプログラミングの手助けをしてくれます。  
ChromebookでもWebから簡単に使えます（ブラウザでアクセス）。

> 📝 ChatGPTと同様に「こんなゲーム作りたい」と相談できるのが特徴。

---

### 👦 小学生でもできる！ゲーム制作フロー

| ステップ | 説明 |
|--------|------|
| ① Claudeに相談 | 例：「Pythonで簡単な迷路ゲーム作って」 |
| ② 返ってきたコードをコピー | Claudeが数秒でコードを提案してくれる |
| ③ VSCodeで貼り付け＆保存 | `game.py`などの名前で保存 |
| ④ ターミナルで実行 | `python3 game.py` |
| ⑤ 改造したいところをClaudeに相談 | 「敵を追加したい」「音を鳴らしたい」なども対応可能 |

---

### 🎁 サンプルプロンプト（Claudeに入力する文）

```
Pythonで、キャラクターが矢印キーで動く簡単な迷路ゲームを作ってください。
できればpygameを使ってください。
```

> 💡 Claudeはとても柔軟に応答するので、思いついたことをどんどん聞いてみましょう！

---

## ✅ まとめ：古いPCでも「学び」の最前線へ

| ツール | 役割 | 特徴 |
|--------|------|------|
| ChromeOS Flex | OS | 軽くて無料。古いPCが蘇る |
| Scratch | 入門アプリ | ブロックで直感的に学べる |
| VSCode | 開発エディタ | 本格プログラミングが可能 |
| Claude | AI補助 | 小学生でも安心のサポート |

---

### 🎯 結論

> **「もう使えない」と思っていたPCが、未来をつくる学習端末になる。**  
>  
> ClaudeやVSCodeの力を借りて、子供たちは自分のアイデアを「形」にできます。

---


## 🙌 最後に

古くなったPCに「学び」という新しい命を吹き込んでみませんか？  
今なら企業から放出されたPCが**5,000円〜10,000円前後**で手に入るチャンスです！

**10年に一度の学習端末化の好機。今すぐチャレンジしてみましょう！**
