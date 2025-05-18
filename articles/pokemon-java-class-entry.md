---
title: ポケモン育成みたいにオブジェクト指向を家族で学べるJava超クラス入門 〜“好き”が学びに変わる魔法の図鑑〜
tags: Java入門 ポケモン 中学生 オブジェクト指向 クラス
author: nakamoto
slide: false
---
# 📚 目次

- 🔹 [第1章 ポケモン図鑑を作ろう！クラスの設計図](#第1章-ポケモン図鑑を作ろうクラスの設計図)
- 🔹 [1.1 オブジェクトとは](#11-オブジェクトとは)
- 🔹 [1.2 クラスを作る](#12-クラスを作る)
- 🔹 [1.3 まとめとテスト](#13-まとめとテスト)
- 🔹 [第2章 モンスターボールからGET！インスタンスの作り方と使い方](#第2章-モンスターボールからgetインスタンスの作り方と使い方)
- 🔹 [2.1 インスタンスを作る](#21-インスタンスを作る)
- 🔹 [2.2 ゲッターとセッターの使い方](#22-ゲッターとセッターの使い方)
- 🔹 [2.3 メソッドを追加する](#23-メソッドを追加する)
- 🔹 [2.4 まとめとテスト](#24-まとめとテスト)
- 🔹 [第3章 ポケモンのひみつを守れ！クラスの仕組み](#第3章-ポケモンのひみつを守れクラスの仕組み)
- 🔹 [3.1 他のクラスからのアクセスを制限する](#31-他のクラスからのアクセスを制限する)
- 🔹 [3.2 メンバの仕組み](#32-メンバの仕組み)
- 🔹 [3.3 コンストラクタの仕組み](#33-コンストラクタの仕組み)
- 🔹 [3.4 まとめとテスト](#34-まとめとテスト)
- 🔹 [第4章 ポケモンを指し示せ！インスタンスと参照の秘密](#第4章-ポケモンを指し示せインスタンスと参照の秘密)
- 🔹 [4.1 参照とは](#41-参照とは)
- 🔹 [4.2 参照を意識する](#42-参照を意識する)
- 🔹 [4.3 完全にイミュータブルなクラスを作ろう！](#43-完全にイミュータブルなクラスを作ろう)
- 🔹 [4.4 参照型](#44-参照型)
- 🔹 [4.5 まとめとテスト](#45-まとめとテスト)
- 🔹 [第5章 オリジナルポケモンを設計せよ！オブジェクト・モデリング](#第5章-オリジナルポケモンを設計せよオブジェクトモデリング)
- 🔹 [5.1 何かの機能を実現するクラス](#51-何かの機能を実現するクラス)
- 🔹 [5.2 record](#52-record)
- 🔹 [5.3 まとめとテスト](#53-まとめとテスト)
- 🔹 [第6章 進化の秘密を解明！継承という血筋](#第6章-進化の秘密を解明継承という血筋)
- 🔹 [6.1 クラス図](#61-クラス図)
- 🔹 [6.2 継承](#62-継承)
- 🔹 [6.3 継承の規則](#63-継承の規則)
- 🔹 [6.4 まとめとテスト](#64-まとめとテスト)
- 🔹 [第7章 ポケモン家系の謎！継承関係を究める](#第7章-ポケモン家系の謎継承関係を究める)
- 🔹 [7.1 継承ツリー](#71-継承ツリー)
- 🔹 [7.2 コンストラクタの連鎖](#72-コンストラクタの連鎖)
- 🔹 [7.3 複数のクラスを1つのファイルにする](#73-複数のクラスを1つのファイルにする)
- 🔹 [7.4 protected修飾子](#74-protected修飾子)
- 🔹 [7.5 まとめとテスト](#75-まとめとテスト)
- 🔹 [第8章 ポケモンの変身術！参照の自動型変換](#第8章-ポケモンの変身術参照の自動型変換)
- 🔹 [8.1 参照の自動型変換](#81-参照の自動型変換)
- 🔹 [8.2 アップキャストとダウンキャスト](#82-アップキャストとダウンキャスト)
- 🔹 [8.3 instanceof演算子](#83-instanceof演算子)
- 🔹 [8.4 switchによる型の判定](#84-switchによる型の判定)
- 🔹 [8.5 まとめとテスト](#85-まとめとテスト)
- 🔹 [第9章 一つの技で多様な効果！ポリモーフィズム（多態性）](#第9章-一つの技で多様な効果ポリモーフィズム多態性)
- 🔹 [9.1 オーバーロード](#91-オーバーロード)
- 🔹 [9.2 オーバーライド](#92-オーバーライド)
- 🔹 [9.3 ポリモーフィズム（多態性）](#93-ポリモーフィズム多態性)
- 🔹 [9.4 まとめとテスト](#94-まとめとテスト)
- 🔹 [第10章 幻のポケモンの謎！抽象クラスの世界](#第10章-幻のポケモンの謎抽象クラスの世界)
- 🔹 [10.1 抽象クラスとは](#101-抽象クラスとは)
- 🔹 [10.2 抽象クラスを継承する](#102-抽象クラスを継承する)
- 🔹 [10.3 抽象クラスのクラス図](#103-抽象クラスのクラス図)
- 🔹 [10.4 まとめとテスト](#104-まとめとテスト)
- 🔹 [第11章 ポケモンのタイプと能力！インタフェースの力](#第11章-ポケモンのタイプと能力インタフェースの力)
- 🔹 [11.1 インタフェースとは](#111-インタフェースとは)
- 🔹 [11.2 インタフェース型への型変換](#112-インタフェース型への型変換)
- 🔹 [11.3 インタフェースによるポリモーフィズム](#113-インタフェースによるポリモーフィズム)
- 🔹 [11.4 インタフェースの継承](#114-インタフェースの継承)
- 🔹 [11.5 まとめとテスト](#115-まとめとテスト)

---

# 🧩 第1章 ポケモン図鑑を作ろう！クラスの設計図

## 🎯 1.1 オブジェクトとは

### 🌟 ポケモンもオブジェクト？実は身近なオブジェクト指向の世界

ポケモンの世界では、ピカチュウやヒトカゲなど、すべてのポケモンが「オブジェクト」です。  
現実世界で例えるなら、「自転車」や「スマートフォン」もオブジェクトです。  

オブジェクトには2つの要素があります：

- 🧬 ** `データ(技ではないものを)` 属性（フィールド）**：たとえばピカチュウの「タイプ」「レベル」など
- 🛠 ** `技` ふるまい（メソッド）**：ピカチュウが使う「10まんボルト」や「なきごえ」などの技

### 🧠 ピカチュウのステータスを集めよう！データをまとめるオブジェクトの魔法

Javaでは、オブジェクトとは「データ（属性）」と「技（操作）」をひとまとめにしたものです。  
例えばピカチュウなら、以下のように表現できます。

```java
// ピカチュウというオブジェクトの一例（擬似コード）
名前: "ピカチュウ"
タイプ: "でんき"
レベル: 15
使える技: 10まんボルト, なきごえ
```

## 🏗 1.2 クラスを作る

### 📘 図鑑に載せる前に！クラスという設計図の大切さ

クラスとは、「オブジェクトの設計図」です。  
たとえば「ポケモン」というクラスがあれば、それをもとにピカチュウ、ヒトカゲなど、色々なポケモンのオブジェクトを作れます。

---

### 🧠 クラスを使うメリットってなに？

ポケモンを「クラス」で定義することで、何が便利になるのでしょうか？  
以下の表にまとめてみました：

| 項目 | 配列や個別変数だけで書く場合 | クラスを使う場合のメリット |
|------|------------------------------|------------------------------|
| 情報のまとまり | name, type, levelを別々に管理 | 1つのオブジェクトでまとめて管理できる |
| 拡張性 | 新しい項目を追加するたびに管理が複雑になる | クラス内に変数やメソッドを追加するだけ |
| 再利用性 | 同じ処理を何度も書く必要がある | メソッドで共通処理をまとめて再利用できる |
| 読みやすさ | 情報のつながりが見えにくい | データとふるまいがセットで直感的 |
| 保守性 | バグが見つかりにくい | クラス内にロジックが集中するので修正しやすい |

---
### 🛠 クラスの定義例（Java）

```java
// ポケモンクラスの定義
public class Pokemon {
    String name; // ポケモンの名前（例：ピカチュウ）
    String type; // タイプ（例：でんき）
    int level;   // レベル（整数で管理）

    // ポケモンが自己紹介するメソッド
    public void introduce() {
        System.out.println("こんにちは！私は" + name + "、タイプは" + type + "、レベルは" + level + "です！");
    }
}
```

📝 このクラスでは、
- `name`：ポケモンの名前を文字列型で管理します。
- `type`：ポケモンのタイプ（例：「ほのお」や「くさ」）を文字列型で管理します。
- `level`：レベルを整数（int型）で管理します。
- `introduce()`：このポケモンの自己紹介を表示するメソッドです。

---

## 🧪 1.3 まとめとテスト

### ✅ ポケモンクラスのまとめ

| 要素 | 内容 |
|------|------|
| クラス | 設計図（ポケモンの共通情報） |
| オブジェクト | 実際に生まれたピカチュウやヒトカゲ |
| 属性 | 名前・タイプ・レベル |
| メソッド | 自己紹介などのふるまい |

---

### 📝 練習問題

1. 自分だけのポケモンを考えて、`Pokemon`クラスで表現してみましょう。
2. `introduce()`メソッドの中で「使える技」も紹介できるように拡張してみよう。

---

### 🔍 解答例（コメント付き）

```java
public class Pokemon { // ポケモンを表すクラス（設計図）
    // ポケモンのデータ（技ではないもの）であるフィールド
    String name;       // ポケモンの名前を保持する文字列型の変数
    String type;       // ポケモンのタイプ（例：でんき、みず等）を保持する変数
    int level;         // ポケモンのレベルを保持する整数型の変数
    String move;       // ポケモンが使える技を文字列で保持する変数

    public void introduce() { // 自己紹介を行うメソッド
        // 名前、タイプ、レベルを出力
        System.out.println("こんにちは！私は" + name + "、タイプは" + type + "、レベルは" + level + "です！");
        // 技の紹介を出力
        System.out.println("わざは「" + move + "」が使えるよ！");
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika = new Pokemon();     // Pokemon型の新しいインスタンスを作成し、変数pikaに代入
        pika.name = "ピカチュウ";           // ピカチュウという名前を設定（文字列）
        pika.type = "でんき";              // タイプを「でんき」に設定
        pika.level = 15;                 // レベルを整数15に設定
        pika.move = "10まんボルト";        // 技を「10まんボルト」に設定

        pika.introduce();               // introduceメソッドを呼び出して自己紹介を表示
    }
}
```

🧩 このように、クラスを使うとポケモン1匹分の情報と動作をセットでまとめて管理できるため、とても便利です。

🧩 このプログラムでは、`Pokemon`クラスを使ってピカチュウの情報を登録し、自己紹介させています。

---

# 🎯 第2章 モンスターボールからGET！インスタンスの作り方と使い方

## 🧱 2.1 インスタンスを作る

### 🥚 ポケモンを召喚せよ！new演算子とコンストラクタの呪文

Javaでは、「new」キーワードを使うことで、クラスからオブジェクト（インスタンス）を生み出します。  
これはまるでモンスターボールからポケモンを出すようなものです！
モンスターボールを投げてポケモンを出す行為を `インスタンス化` と言います。

つまり、モンスターボールを投げ（インスタンス化）ることで、ピカチュウ（インスタンス）が出てきます。

```java
Pokemon pika = new Pokemon();
```

- `Pokemon`：設計図（クラス）の名前
- `pika`：作られたピカチュウのインスタンス（オブジェクト）
- `new Pokemon()`：新しいポケモンを作る魔法の呪文（コンストラクタの呼び出し）



📝 これは「Pokemon型の変数pikaを定義し、newで生成したオブジェクトを代入している」処理です。

---

## 🔓 2.2 ゲッターとセッターの使い方

### 🔍 「きみのHPはいくつ？」ゲッターでステータスを確認

ゲッターとは、ポケモンの情報（フィールド）を取り出すためのメソッドです。
ゲッター

```java
public String getName() {
    return name; // 文字列型変数nameの値を返す
}
```

---

### 💪 「レベルアップ！」セッターでポケモンを強化する

セッターは、ポケモンの情報を変更したいときに使います。

```java
public void setLevel(int lvl) {
    level = lvl; // int型変数lvlの値をint型変数levelに代入する
}
```

## 🔍ゲッター（getter）とセッター（setter）を使う理由

Javaのオブジェクト指向において「ゲッター（getter）とセッター（setter）」を使う理由は、**カプセル化（encapsulation）**を利用するためです
カプセル化では、クラス内部のデータ（フィールド）を**安全に管理し、意図しない操作を防ぐ**ことができます。

---

## 🧬 カプセル化ってなに？

カプセル化とは、

> 「クラス内部のデータは勝手に外部から直接変更できないようにして、安全に取り扱う方法」

たとえば、ポケモンのHP（体力）を考えてみましょう。

---

## 🧪 ❌ ゲッター・セッターを使わない例（よくない）

```java
// Pokemonクラスを定義（ポケモンの情報を持つクラス）
public class Pokemon {
    public int hp;  // HPの変数。publicなので他のクラスから自由にアクセスできてしまう
}

// 実行用のMainクラス
public class Main {
    public static void main(String[] args) {
        // Pokemonクラスのインスタンスを作成して、pikachuという名前をつける
        Pokemon pikachu = new Pokemon();

        // pikachuのHPに直接 -100 を代入（不正な値だが、publicなので代入できてしまう）
        pikachu.hp = -100;
    }
}
```

### 問題点：

🚨 このコードの問題点：
hpがpublicのため、どこからでも直接代入できてしまう。

その結果、-100 のようなゲームのルールに反する値も簡単に入り、バグの原因になる。

---

## ✅ ゲッター・セッターを使う正しい例

```java
// Pokemonクラスを定義（ポケモンの情報を持つクラス）
public class Pokemon {
    // HPの変数。privateにすることで外部から直接アクセスできなくする
    private int hp;

    // HPを設定するためのメソッド（セッター）
    public void setHp(int hp) {
        // if文で条件をチェックする：引数hpが0以上か？
        if (hp >= 0) {
            // 0以上なら、this.hp（フィールド）に値を設定
            this.hp = hp;
        } else {
            // もし0未満なら、エラーメッセージを表示（代入は行わない）
            System.out.println("HPは0以上でなければなりません。");
        }
    }

    // HPの値を取得するためのメソッド（ゲッター）
    public int getHp() {
        // フィールドのhpを返す
        return this.hp;
    }
}

// 実行用のMainクラス
public class Main {
    public static void main(String[] args) {
        // Pokemonクラスのインスタンスを作成してpikachuと名付ける
        Pokemon pikachu = new Pokemon();

        // pikachuのHPに100をセット（0以上なので正しく代入される）
        pikachu.setHp(100);

        // 現在のpikachuのHPを表示（→ 100）
        System.out.println(pikachu.getHp());

        // pikachuのHPに-50をセットしようとする（不正な値なので拒否される）
        pikachu.setHp(-50);

        // 再度HPを表示（→ 前回の100のまま変更されていない）
        System.out.println(pikachu.getHp());
    }
}

```

### 🔍 if (hp >= 0) の各行の説明まとめ

| 行番号                        | 内容    | 説明                        |
| -------------------------- | ----- | ------------------------- |
| `if (hp >= 0)`             | 条件文   | hpが0以上なら true、0未満なら false |
| `{ this.hp = hp; }`        | 真のとき  | 正常な値なのでフィールドに代入           |
| `else {`                   | 偽のとき  | 不正な値だった場合の処理に進む           |
| `System.out.println(...);` | エラー出力 | 値が不正であることをユーザーに知らせる       |

---

### ✅ 出力例：

```
100
HPは0以上でなければなりません。
100
```


### 🎮 実行の流れと出力結果

```
🔢 ステップ 1：正しい値を設定
-----------------------------------
🧠 コード実行：
    pikachu.setHp(100);

✅ 判定：100 は 0 以上なので OK  
💾 処理結果：this.hp = 100 に設定

🖨 出力：
    System.out.println(pikachu.getHp());
📢 コンソール表示：
    👉 100
```

```
🔢 ステップ 2：不正な値を設定
-----------------------------------
🧠 コード実行：
    pikachu.setHp(-50);

❌ 判定：-50 は 0 未満 → NG  
🚫 処理結果：hp の値は変更されない

🖨 出力：
    System.out.println("HPは0以上でなければなりません。");
📢 コンソール表示：
    ⚠️ HPは0以上でなければなりません。
```

```
🔢 ステップ 3：HPを再確認
-----------------------------------
🧠 コード実行：
    System.out.println(pikachu.getHp());

🗂 現在の hp：100（前のステップで変更されていない）

📢 コンソール表示：
    👉 100
```

---

### 🧾 最終的な出力まとめ

```
100
HPは0以上でなければなりません。
100
```

---

## 🎯 ゲッターセッターメリットまとめ

ゲッターとセッターを使うことで、**ポケモンの能力値を正しく、安全に管理**できるようになります。
ゲームで言えば、「ズルしてHPをMAXにする」みたいなことが起こらないように、きちんと**チェックポイントを作る**のがゲッター・セッターの役目です。

| 🧩 項目       | ✅ メリット            | 🔍 ポケモンの例                     |
| ----------- | ----------------- | ----------------------------- |
| **安全性の向上**  | 不正な値の代入を防ぐ        | HPがマイナスや9999にならないように制御できる     |
| **柔軟性の確保**  | 将来の変更に対応しやすい      | 「レベルが50以上のときだけ進化できる」など条件追加もOK |
| **可読性・管理性** | クラスの使い方が明確になる     | ゲッターだけ使えば読み取り専用にもできる          |
| **隠蔽性の強化**  | 内部構造を隠して外部に依存させない | カプセル化により能力の計算ロジックなどを外から見せずに守れる        |



---

### ✨ ゲッター・セッター付きのPokemonクラス

#### 🧠 このクラスの役割まとめ：
`private` で定義された4つの情報（名前、タイプ、レベル、技）を安全に管理。
`set～` メソッドで値を設定（書き込み）。
`get～` メソッドで値を取得（読み取り）。

これは「カプセル化」の基本であり、外部から安全にポケモンの情報を扱うための方法です。

```

```java
// Pokemonクラスの定義（ポケモンの基本情報を表す）
public class Pokemon {

    // ポケモンの名前を表すフィールド（外部から直接アクセスできないようにprivate）
    private String name;

    // ポケモンのタイプ（例：でんき、ほのお など）を表すフィールド
    private String type;

    // ポケモンのレベル（数値）を表すフィールド
    private int level;

    // ポケモンが覚えている技の名前を表すフィールド
    private String move;

    // 名前を設定するセッターメソッド（引数で受け取った値をnameに代入）
    public void setName(String name) { this.name = name; }

    // タイプを設定するセッターメソッド
    public void setType(String type) { this.type = type; }

    // レベルを設定するセッターメソッド
    public void setLevel(int level) { this.level = level; }

    // 技（move）を設定するセッターメソッド
    public void setMove(String move) { this.move = move; }

    // 名前を取得するゲッターメソッド（現在のnameの値を返す）
    public String getName() { return name; }

    // タイプを取得するゲッターメソッド
    public String getType() { return type; }

    // レベルを取得するゲッターメソッド
    public int getLevel() { return level; }

    // 覚えている技を取得するゲッターメソッド
    public String getMove() { return move; }
}
```

---

## 🛠 2.3 メソッドを追加する


### ⚡ 「10まんボルト」実装大作戦！技を使うメソッドを作ろう

```java
public void useMove() {
    System.out.println(name + "の" + move + "！こうかはばつぐんだ！");
}
```

📝 このメソッドは、ポケモンがわざを使ったときの表示を再現します。

---

##  ✅ 応用編： `@Override` と `toString`

### 📢 `応用編` 「ピカチュウ、自己紹介して！」toStringメソッドの秘密



```java

// @Override を付けることで、「これは親クラスの toString を上書きしてますよ！」ということをコンパイラに伝えています。
@Override

// toString() を独自に定義することで、System.out.println(pokemon) のように書いたときにわかりやすい文字列で表示されるようにしています。
public String toString() {
    return "ポケモン：" + name + " / タイプ：" + type + " / レベル：" + level + " / わざ：" + move;
}
```


### 🧩 `@Override` は 必須ではありませんが、強く推奨される記述です。

`@Override` は、親クラス（この場合は Object）のメソッドを上書きしていることを明示する **アノテーション（注釈）** です。

Javaでは、すべてのクラスが `Object` クラスを暗黙的に継承しており、 `toString()` は `Object` クラスに定義されています。

`toString()`は、オブジェクトの内容を文字列で表示する特別なメソッドです。

`@Override` を付けなくても動作する。

`@Override` を付けていればコンパイルエラーになり、ミスに気づける
付けなければ、オーバーライドにならずにバグになる

---


## 🎯 2.4 まとめとテスト

### ✅ インスタンス操作のポイント

#### 🎮基本

| 用語 | 説明 |
|------|------|
| インスタンス | new演算子で作成したオブジェクト |
| ゲッター | フィールドの値を取得するメソッド |
| セッター | フィールドの値を設定するメソッド |

#### 📢応用

| 用語 | 説明 |
|------|------|
| `@Override` | 親クラス（この場合は Object）のメソッドを上書きしていることを明示する**アノテーション（注釈）**|
| `toString` | オブジェクトの状態を文字列に変換 |
| 任意メソッド | オリジナル技や動作を実装 |

---

### 🧪 動作確認！最終サンプルコード

```java
public class Pokemon {
    private String name;
    private String type;
    private int level;
    private String move;

    public void setName(String name) { this.name = name; }
    public void setType(String type) { this.type = type; }
    public void setLevel(int level) { this.level = level; }
    public void setMove(String move) { this.move = move; }

    public String getName() { return name; }
    public String getType() { return type; }
    public int getLevel() { return level; }
    public String getMove() { return move; }

    public void useMove() {
        System.out.println(name + "の" + move + "！こうかはばつぐんだ！");
    }

    @Override
    public String toString() {
        return "ポケモン：" + name + " / タイプ：" + type + " / レベル：" + level + " / わざ：" + move;
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika = new Pokemon(); // Pokemon型オブジェクトpikaを生成
        pika.setName("ピカチュウ");     // 名前を設定
        pika.setType("でんき");         // タイプを設定
        pika.setLevel(25);             // レベルを設定
        pika.setMove("10まんボルト");    // わざを設定

        System.out.println(pika);      // オブジェクト内容を出力
        pika.useMove();                // わざを使う
    }
}
```

🧩 このサンプルで、**クラス → インスタンス生成 → 値の設定 → メソッドの実行**という一連の流れを体験できます！

---

# 🛡 第3章 ポケモンのひみつを守れ！クラスの仕組み

## 🔐 3.1 他のクラスからのアクセスを制限する

### 🧳 「そのHPは見せられない！」privateとpublicの境界線

ポケモンの「HP」や「覚えている技」は、ほかのトレーナーから勝手に見られたら困るかもしれませんよね？  
Javaでは、「アクセス修飾子」を使って、クラスの中の情報を守ることができます。

```java
public class Pokemon {
    private int hp; // 他のクラスからは直接見えないようにする（非公開）

    public int getHp() {
        return hp; // 値を返す（公開）
    }

    public void setHp(int hp) {
        this.hp = hp; // 外部から値を設定する方法を用意（公開）
    }
}
```

📝 `private`は**非公開**、`public`は**公開**を意味します。

---

### 🧩 グレーゾーンの属性！修飾子なしの不思議な世界

アクセス修飾子を何も書かなかった場合、同じパッケージの中からはアクセスできます。  
これを「デフォルト（パッケージ）アクセス」と呼びます。  
✨️独自仕様：Javaでは明示的にアクセス範囲を決めることで安全性を保つのが基本です。

---

### 🛡 秘密のステータスを保護せよ！カプセル化の真髄

**カプセル化**とは、「データをクラスの中に閉じ込めて、外部からの不正なアクセスを防ぐこと」です。  
ポケモンでいえば、「ステータス画面はトレーナーだけが操作できる」状態ですね！

---

## ⚙️ 3.2 メンバの仕組み

### ⚡ 「全ポケモン共通の特性」スタティックメンバの超パワー

すべてのポケモンに共通する特性、たとえば「ポケモンの世界共通の最大レベル」は`static`で表現できます。

```java
public class Pokemon {
    public static final int MAX_LEVEL = 100; // 全ポケモン共通の最大レベル
}
```

📝 `static`は**クラス全体で共通の変数やメソッド**を意味します。

---

### 🧬 「このピカチュウだけの特性」インスタンスメンバの個性

一方、各ポケモンが持つ「レベル」や「名前」などは**インスタンスメンバ**です。

```java
public class Pokemon {
    private int level; // このポケモンだけが持つ個別の値
}
```

---

### ⚠️ スタティックとインスタンス、共存できるの？

もちろんできますが、違いをしっかり意識することが大切です。

```java
public class Pokemon {
    public static final int MAX_LEVEL = 100;
    private int level;

    public boolean isMaxLevel() {
        return level == MAX_LEVEL; // クラス変数との比較
    }
}
```

---

## 🧱 3.3 コンストラクタの仕組み

### 🌀 同じ名前で違う生まれ方？オーバーロードの魔法

Javaでは、**コンストラクタを複数持たせる（オーバーロード）**ことができます。  
これは、いろいろな条件でポケモンを生み出す技のようなものです。

```java
public Pokemon() {
    this.name = "ピカチュウ"; // デフォルトの名前を設定
}

public Pokemon(String name) {
    this.name = name; // 引数で指定された名前を使う
}
```

---

### 🌈 「色違いポケモン」も作れる！コンストラクタを増やす技

```java
public Pokemon(String name, int level, String type) {
    this.name = name;       // 名前をセット
    this.level = level;     // レベルをセット
    this.type = type;       // タイプをセット
}
```

---

### 🔁 「this」で簡単！コンストラクタの連携プレイ

```java
public Pokemon(String name, int level) {
    this(name, level, "ノーマル"); // 他のコンストラクタを呼び出す
}
```

📝 `this()`は「同じクラス内の別のコンストラクタを呼び出す」特別な書き方です。

---

### 🧊 何も指定しなくても生まれるポケモン？デフォルトコンストラクタの謎

コンストラクタを定義しないと、Javaは自動で**デフォルトコンストラクタ（引数なし）**を用意してくれます。

しかし、他にコンストラクタがあると自動生成されません。注意しましょう！

---

## 🧪 3.4 まとめとテスト

### 📘 第3章まとめ：カプセル化とメンバ管理の極意

| 項目 | 内容 |
|------|------|
| アクセス修飾子 | データの見せる／見せないを設定する方法 |
| private | 他のクラスからは見えない |
| public | どこからでも使える |
| static | 全ポケモン共通の性質（例：MAX_LEVEL） |
| コンストラクタ | ポケモンを生み出すための特別なメソッド |
| this | 自分自身を指す／他のコンストラクタを呼び出す |

---

### 🎮 テストコード：ここまでの総まとめ

```java
public class Pokemon {
    private String name;
    private String type;
    private int level;
    public static final int MAX_LEVEL = 100;

    public Pokemon() {
        this("ピカチュウ", 5, "でんき");
    }

    public Pokemon(String name, int level, String type) {
        this.name = name;
        this.level = level;
        this.type = type;
    }

    public String getName() { return name; }
    public String getType() { return type; }
    public int getLevel() { return level; }

    public void setLevel(int level) { this.level = level; }

    public boolean isMaxLevel() {
        return level == MAX_LEVEL;
    }

    public void introduce() {
        System.out.println("私は" + name + "！タイプ：" + type + "、レベル：" + level);
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika = new Pokemon(); // デフォルトのピカチュウを生成
        pika.introduce(); // 自己紹介

        Pokemon eve = new Pokemon("イーブイ", 10, "ノーマル");
        eve.introduce();

        System.out.println("イーブイは最大レベル？：" + eve.isMaxLevel());
    }
}
```

🧩 このサンプルでは、**カプセル化・static・コンストラクタオーバーロード**をすべて体験できます！

---

# 🧭 第4章 ポケモンを指し示せ！インスタンスと参照の秘密

## 🎯 4.1 参照とは

### 🎈 モンスターボールとポケモンの関係？参照の不思議な役割

ポケモンの世界では、「モンスターボール」はポケモンを**しまっておくケース**のようなもの。  
Javaでは、このモンスターボールが「**参照（Reference）**」にあたります。

```java
Pokemon pika1 = new Pokemon(); // ポケモンを1体作る
Pokemon pika2 = pika1;         // pika1のポケモンを、pika2にも渡す
```

📝 `pika2`は`pika1`と**同じポケモンを指し示しているだけ**で、別のポケモンではありません。

---

## 👀 4.2 参照を意識する

### 🧪 「コピーしたはずなのに同じポケモン!?」変数間の代入の真実

```java
pika2.setLevel(50); // pika2でレベルを変更すると…
System.out.println(pika1.getLevel()); // pika1でも反映されている！
```

📌 オブジェクトは**本体ではなく「場所（アドレス）」を変数が指している**と理解しましょう。

---

### ✨️独自仕様：「ポケモンの個体値」を考慮した場合の注意

もし「まったく同じ見た目だけど別の個体のピカチュウ」が必要な場合は、**コピーを作る仕組み**が必要になります。

---

## 🧊 4.3 完全にイミュータブルなクラスを作ろう！

### 🧼 「誰も変えられない伝説のポケモン」完全イミュータブルの実装法

```java
public final class Pokemon {
    private final String name;
    private final String type;
    private final int level;

    public Pokemon(String name, String type, int level) {
        this.name = name;
        this.type = type;
        this.level = level;
    }

    public String getName() { return name; }
    public String getType() { return type; }
    public int getLevel() { return level; }
}
```

🛡 このクラスでは、すべてのフィールドが`final`で、**一度決めたら二度と変えられません。**

---

## 🧬 4.4 参照型

### 🧪 「プリミティブ型との違いは？」Java言語の型システム解剖

| 型の種類 | 例 | 特徴 |
|----------|----|------|
| プリミティブ型 | `int`, `double`, `boolean` | 値そのものを扱う |
| 参照型 | `String`, `Pokemon`, `List` | オブジェクトの**場所（参照）**を扱う |

---

### ⚠️ 「空っぽのモンスターボール？」nullの正体と危険性

```java
Pokemon pika = null; // まだ何も入っていないモンスターボール
pika.introduce();    // ← これをするとエラー！（NullPointerException）
```

🚨 `null`は「まだ中身がない」状態なので、呼び出そうとすると**クラッシュします！**

---

## 🧪 4.5 まとめとテスト

### 🧾 第4章まとめ：参照とイミュータブルの理解

| キーワード | 内容 |
|------------|------|
| 参照 | オブジェクトの場所（アドレス）を指す |
| 同じ参照 | 変数を代入すると**同じオブジェクトを参照**する |
| null | 何も入っていない状態。アクセスするとエラー |
| イミュータブル | 値が一切変わらないようにする設計 |

---

### 🧪 総合テストコード

```java
public final class Pokemon {
    private final String name;
    private final String type;
    private final int level;

    public Pokemon(String name, String type, int level) {
        this.name = name;
        this.type = type;
        this.level = level;
    }

    public String getName() { return name; }
    public String getType() { return type; }
    public int getLevel() { return level; }

    public void introduce() {
        System.out.println("私は" + name + "！タイプ：" + type + "、レベル：" + level);
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika1 = new Pokemon("ピカチュウ", "でんき", 25);
        Pokemon pika2 = pika1; // 同じポケモンを参照

        pika1.introduce();
        pika2.introduce(); // 同じ内容が出力される

        // nullポケモンの例（コメントアウトしないと実行時エラー）
        // Pokemon empty = null;
        // empty.introduce(); // NullPointerException
    }
}
```

🔍 参照とは何か、nullとはどう危険なのかをこのコードでしっかり体験しよう！

---

# 🧪 第5章 オリジナルポケモンを設計せよ！オブジェクト・モデリング

## 🧱 5.1 何かの機能を実現するクラス

### 📝 「どんなポケモンを作る？」処理の全体像を考えよう

ポケモンゲームでは、名前、タイプ、レベル、覚えている技など、さまざまな情報が必要です。  
これを**クラスでどう表現するか**を考えるのが「オブジェクト・モデリング」です。

---

### 🧮 「特性と技を決めよう」クラス定義の設計図を描く

```java
public class Pokemon {
    private String name;      // ポケモンの名前（例：フシギダネ）
    private String type;      // ポケモンのタイプ（例：くさ）
    private int level;        // レベル（整数で表現）
    private String[] moves;   // 覚えている技を配列で管理

    public Pokemon(String name, String type, int level, String[] moves) {
        this.name = name;
        this.type = type;
        this.level = level;
        this.moves = moves;
    }

    public void introduce() {
        System.out.println("名前：" + name + " / タイプ：" + type + " / レベル：" + level);
        System.out.println("覚えている技：");
        for (String move : moves) {
            System.out.println("- " + move);
        }
    }
}
```

📝 このクラスは、基本情報と技の一覧を保持し、自己紹介メソッドで出力するようになっています。

---

### 🚀 「本当にこれでいい？」最終仕様の見直しポイント

- 技は何個まで？ → 今回は配列で自由に対応
- レベルの上限は？ → static final で固定可能
- 複数のタイプはどうする？ → ✨️独自仕様：今回は1タイプのみに限定

---

### ⚙️ 「いざ実装！」設計図からコードへの変換テクニック

```java
String[] fushiMoves = {"たいあたり", "つるのムチ", "どくのこな"};
Pokemon fushigidane = new Pokemon("フシギダネ", "くさ", 10, fushiMoves);
fushigidane.introduce();
```

📝 `String[]`を使って複数の技をまとめて管理し、クラスに渡しています。

---

## 📦 5.2 record

### 🆕 「Java 16の新機能！」recordって何者？

Java 16以降では、**簡単にデータクラスを定義できる構文**として`record`が導入されました。

```java
public record SimplePokemon(String name, String type, int level) {}
```

---

### ✨️「簡単ポケモン図鑑エントリ」recordの定義と便利機能

recordは、
- `コンストラクタ`
- `getter`
- `toString()`
- `equals()`  
などを自動で作ってくれるため、コードが短くなります。

```java
SimplePokemon zenigame = new SimplePokemon("ゼニガメ", "みず", 8);
System.out.println(zenigame.name());  // getterのように値が取れる
System.out.println(zenigame);         // 自動でtoStringが使われる
```

---

### 🧠 「もっと強化したい！」recordに機能を追加する方法

recordにもメソッドを追加できます。

```java
public record SimplePokemon(String name, String type, int level) {
    public boolean isStarter() {
        return level <= 10;
    }
}
```

---

### 🔒 「絶対に変わらない伝説のポケモン」完全イミュータブルrecord

recordは**すべてのフィールドがfinal（変更不可）**です。  
まさに「ミュウツー」や「ルギア」のような、伝説ポケモンにふさわしい設計です。

---

### 🪄 「3行でポケモン作成！」超簡単record活用術

```java
SimplePokemon hitokage = new SimplePokemon("ヒトカゲ", "ほのお", 5);
System.out.println("スタメン候補：" + hitokage.name());
```

---

## 🎯 5.3 まとめとテスト

### ✅ モデリングとrecordのポイント

| 概念 | 説明 |
|------|------|
| モデリング | 現実世界（ポケモン）をプログラムで再現する設計 |
| フィールド | ポケモンの名前、タイプ、技などの情報 |
| メソッド | 自己紹介や技の実行などの動作 |
| record | 簡易データクラス（不変・軽量） |
| イミュータブル | 値が変わらない安全なオブジェクト |

---

### 💻 総合サンプルコード

```java
public class Pokemon {
    private String name;
    private String type;
    private int level;
    private String[] moves;

    public Pokemon(String name, String type, int level, String[] moves) {
        this.name = name;
        this.type = type;
        this.level = level;
        this.moves = moves;
    }

    public void introduce() {
        System.out.println("名前：" + name + " / タイプ：" + type + " / レベル：" + level);
        System.out.println("覚えている技：");
        for (String move : moves) {
            System.out.println("- " + move);
        }
    }
}

public record SimplePokemon(String name, String type, int level) {
    public boolean isStarter() {
        return level <= 10;
    }
}

public class Main {
    public static void main(String[] args) {
        String[] moves = {"たいあたり", "つるのムチ", "どくのこな"};
        Pokemon bulbasaur = new Pokemon("フシギダネ", "くさ", 10, moves);
        bulbasaur.introduce();

        SimplePokemon charmander = new SimplePokemon("ヒトカゲ", "ほのお", 5);
        System.out.println("スタメン候補：" + charmander.name());
        System.out.println("スターター？：" + charmander.isStarter());
    }
}
```

🧩 このコードでは、クラスによるモデルとrecordによる軽量データ定義の両方が体験できます！

---

# 🧬 第6章 進化の秘密を解明！継承という血筋

## 📊 6.1 クラス図

### 📚 「ポケモン図鑑の裏側」クラス図の読み解き方

Javaの継承は、**図鑑の進化ツリー**のようなものです。  
例えば「ピチュー → ピカチュウ → ライチュウ」の関係をクラス図で表すと、以下のようになります。

```
Pokemon（親クラス）
  └─ Pikachu（子クラス）
       └─ Raichu（孫クラス）
```

📝 このように、「共通する情報」は親クラスに、「進化して追加される情報」は子クラスに記述します。

---

### ✨️独自仕様：クラス図ツールがない場合はテキストで描いてもOK！

---

## 🧪 6.2 継承

### 👪 「ピチューからピカチュウへ」継承でクラスを拡張する方法

```java
public class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("私は" + name + "タイプは" + type + "です！");
    }
}

public class Pikachu extends Pokemon {
    int level;

    public void thunderbolt() {
        System.out.println(name + "の10まんボルト！");
    }
}
```

📝 `Pikachu`クラスは`Pokemon`クラスを**継承**して、`level`と`thunderbolt`という追加要素を持たせています。

---

### 🐣 「卵からの孵化」インスタンス初期化の順序と仕組み

Javaでは、親クラスのコンストラクタが先に呼ばれ、次に子クラスのコンストラクタが呼ばれます。

```java
public class Pokemon {
    public Pokemon() {
        System.out.println("ポケモンが誕生！");
    }
}

public class Pikachu extends Pokemon {
    public Pikachu() {
        System.out.println("ピカチュウが生まれた！");
    }
}
```

結果は以下の順番で表示されます：

```
ポケモンが誕生！
ピカチュウが生まれた！
```

---

### 🚀 「進化するとできること」継承の効果を実感しよう

```java
Pikachu pika = new Pikachu();
pika.name = "ピカチュウ";
pika.type = "でんき";
pika.level = 15;

pika.introduce();     // 親クラスのメソッド
pika.thunderbolt();   // 自分のメソッド
```

---

## 📜 6.3 継承の規則

### 🧠 「〇〇は〇〇である」Is-a関係の重要性

「ピカチュウはポケモンである」このような**Is-a**の関係が成立するのが継承です。  
逆に「ポケモンはピカチュウである」は成立しないため、**逆の継承**はできません。

---

### 🚫 「伝説のポケモンは複製できない」継承できないクラスの秘密

```java
public final class Mewtwo extends Pokemon {
    // このクラスは継承できません（final）
}
```

📝 `final`をつけると、そのクラスは**これ以上進化（継承）されない**ようにできます。

---

### 🔒 「封印された特性」シールクラスの不思議な力

✨️独自仕様：**sealed class（Java 17〜）**を使うと、**継承できるクラスを限定**できます。

```java
public sealed class Pokemon permits Pikachu, Eevee {}
```

この場合、`Pokemon`を継承できるのは`Pikachu`と`Eevee`だけです。

---

### 🧙 「一子相伝の技」継承できないメンバの特徴

- `private`なフィールドやメソッドは子クラスでは使えません。
- `final`なメソッドはオーバーライドできません。

---

## 🎯 6.4 まとめとテスト

### 📘 継承のまとめ

| 概念 | 説明 |
|------|------|
| 継承（extends） | クラスの機能を引き継ぐ |
| 親クラス | 基本の共通機能を持つクラス |
| 子クラス | 特定の追加機能を持つクラス |
| Is-a関係 | ○○は××である、という関係 |
| final | それ以上継承できない |
| sealed（Java17） | 継承先を限定する（✨️独自仕様） |

---

### 💻 総合サンプルコード

```java
public class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("私は" + name + "、タイプは" + type + "です！");
    }
}

public class Pikachu extends Pokemon {
    int level;

    public Pikachu(String name, int level) {
        this.name = name;
        this.type = "でんき";
        this.level = level;
    }

    public void thunderbolt() {
        System.out.println(name + "の10まんボルト！ こうかはばつぐんだ！");
    }
}

public class Main {
    public static void main(String[] args) {
        Pikachu pika = new Pikachu("ピカチュウ", 20); // Pikachuクラスのインスタンス作成
        pika.introduce();       // 親クラスのメソッドを呼び出す
        pika.thunderbolt();     // 子クラス独自のメソッドを呼び出す
    }
}
```

🧩 このサンプルで、継承・コンストラクタ・オーバーライド・親子関係すべてを実践しよう！

---

# 🧬 第7章 ポケモン家系の謎！継承関係を究める

## 🌳 7.1 継承ツリー

### 🧭 「ポケモン進化の樹形図」継承ツリーの全体像

ポケモンには家系図のような進化の系統があります。  
Javaでも「継承ツリー」として、親子関係を構築できます。

例）ニャース → ニャイキング（✨️独自仕様：地方進化）

```
Pokemon
├── Meowth
│   └── Perrserker
└── Eevee
    ├── Vaporeon
    ├── Jolteon
    └── Flareon
```

---

### 🧬 「全てのポケモンのご先祖様」Objectクラスの秘密

Javaのすべてのクラスは、暗黙的に `Object` クラスを継承しています。

```java
public class Pikachu {
    // 実は Object クラスの toString() や equals() などが使える
}
```

📝 これにより、どのクラスにも標準機能が備わっているのです。

---

## 🔗 7.2 コンストラクタの連鎖

### 👶 「親から子へ、受け継がれる初期化」コンストラクタの連鎖の仕組み

親クラスと子クラスのコンストラクタは、**順番に呼ばれる**必要があります。

```java
public class Pokemon {
    public Pokemon(String name) {
        System.out.println(name + " が生まれた！");
    }
}

public class Eevee extends Pokemon {
    public Eevee() {
        super("イーブイ"); // 親クラスのコンストラクタを呼び出す
        System.out.println("イーブイが準備完了！");
    }
}
```

出力結果：

```
イーブイ が生まれた！
イーブイが準備完了！
```

---

### ❓ 「書かなくても呼ばれる？」super()省略時の挙動

引数なしのコンストラクタが親クラスに存在する場合、`super()`の記述がなくても呼び出されます。  
ただし、**引数ありのコンストラクタしかないときは、super()を明示する必要あり**！

---

## 📁 7.3 複数のクラスを1つのファイルにする

### 📄 「進化前と進化後を一緒に！」複数クラス定義のテクニック

```java
public class Pokemon {
    String name;
    public void greet() {
        System.out.println("やあ、" + name + "だよ！");
    }
}

class Pikachu extends Pokemon {
    public Pikachu() {
        name = "ピカチュウ";
    }
}
```

📝 ファイル名が`Pokemon.java`なら、`public`がつくクラスは1つだけ。残りは`public`を付けないことで共存可能です。

---

## 🛡 7.4 protected修飾子

### 🏠 「家族だけに見せる特性」protectedの特殊な力

```java
public class Pokemon {
    protected String name; // 自分と子クラス、同じパッケージ内のクラスからアクセスOK
}
```

---

### ⚠️ 「使い方を間違えると危険！」protected利用時の注意点

- 外部からアクセスできないとは限らない  
- **パッケージをまたぐと制限される**

---

### 🌐 「public、private、protected、無印」アクセス修飾子の使い分け

| 修飾子 | 同じクラス内 | 同じパッケージ内 | 子クラス | 外部クラス |
|--------|---------------|------------------|-----------|-------------|
| public | ○             | ○                | ○         | ○           |
| protected | ○          | ○                | ○         | ×（異パッケージ） |
| （なし） | ○            | ○                | ×         | ×           |
| private | ○            | ×                | ×         | ×           |

---

## 🎯 7.5 まとめとテスト

### 🧾 第7章まとめ：Javaの家系図を完全理解！

| 概念 | 内容 |
|------|------|
| 継承ツリー | クラス間の親子関係を構造的に表現 |
| Objectクラス | すべてのクラスのご先祖さま |
| super() | 親クラスのコンストラクタ呼び出し |
| protected | パッケージと子クラスから見える属性 |

---

### 💻 総合サンプルコード

```java
public class Pokemon {
    protected String name;

    public Pokemon(String name) {
        this.name = name;
        System.out.println(name + " が生まれた！");
    }

    public void greet() {
        System.out.println("こんにちは！私は " + name + " です！");
    }
}

class Pikachu extends Pokemon {
    public Pikachu() {
        super("ピカチュウ"); // 親クラスのコンストラクタ呼び出し
        System.out.println("ピカチュウの準備完了！");
    }

    public void thunderbolt() {
        System.out.println(name + " の 10まんボルト！");
    }
}

public class Main {
    public static void main(String[] args) {
        Pikachu pika = new Pikachu();
        pika.greet();           // 親クラスのメソッド
        pika.thunderbolt();     // 子クラス独自の技
    }
}
```

🎉 この章では、**継承の構造・protected・クラスの共存と生成順**までマスターできます！

---

# 🌀 第8章 ポケモンの変身術！参照の自動型変換

## 🪄 8.1 参照の自動型変換

### 🔁 「メタモンの変身」参照の自動型変換とは？

Javaでは、子クラスのオブジェクトを親クラスの型として扱うことができます。  
これは、まるで**メタモンが他のポケモンに変身**して、他のポケモンとして行動しているようなイメージです！

```java
Pokemon pika = new Pikachu("ピカチュウ", 20);
pika.introduce(); // 親クラスのメソッドは使える
```

📝 子クラス`Pikachu`のインスタンスが、親クラス`Pokemon`型の変数に代入されている。

---

## 🧱 8.2 アップキャストとダウンキャスト

### ⬆️ 「ピカチュウをポケモンとして扱う」アップキャスト

アップキャストとは、**子クラス → 親クラス** への変換です。（自動で行われます）

```java
Pokemon poke = new Pikachu("ピカチュウ", 20);
```

---

### ⬇️ 「ポケモンの正体はピカチュウだった！」ダウンキャスト

ダウンキャストとは、**親クラス → 子クラス**への変換です。  
こちらは**明示的にキャスト**が必要です。

```java
Pikachu pika = (Pikachu) poke; // 明示的なキャスト
pika.thunderbolt(); // 子クラス独自のメソッドが使える！
```

⚠️ もしpokeが`Pikachu`以外だった場合、`ClassCastException`というエラーになります！

---

## 🔍 8.3 instanceof演算子

### 🧪 「それってほんとにピカチュウ？」instanceofで正体を見破る方法

```java
if (poke instanceof Pikachu) {
    Pikachu pika = (Pikachu) poke; // 安全にキャストできる！
    pika.thunderbolt();
}
```

📝 `instanceof`は「このインスタンスはこの型か？」を確認できる便利な道具です。

---

## 🧠 8.4 switchによる型の判定

### 🌀 「タイプによって技が変わる」switch文とswitch式の威力（Java 14〜）

✨️独自仕様：Java 14以降で使える「型のパターンマッチング付きswitch」

```java
switch (poke) {
    case Pikachu p -> p.thunderbolt();
    case Eevee e -> e.adapt();
    default -> System.out.println("未知のポケモン！");
}
```

📝 switch文でもinstanceofとキャストを同時に行うことができるようになりました。

---

## 🎯 8.5 まとめとテスト

### 📘 変身の極意：まとめ

| 用語 | 説明 |
|------|------|
| アップキャスト | 子 → 親（自動） |
| ダウンキャスト | 親 → 子（明示） |
| instanceof | 型を安全に確認 |
| switch式 | 型分岐を簡単に表現（Java 14以降） |

---

### 💻 総合サンプルコード

```java
public class Pokemon {
    protected String name;
    public Pokemon(String name) {
        this.name = name;
    }
    public void introduce() {
        System.out.println("私は " + name + " です！");
    }
}

class Pikachu extends Pokemon {
    private int level;
    public Pikachu(String name, int level) {
        super(name);
        this.level = level;
    }
    public void thunderbolt() {
        System.out.println(name + " の 10まんボルト！ レベル：" + level);
    }
}

class Eevee extends Pokemon {
    public Eevee(String name) {
        super(name);
    }
    public void adapt() {
        System.out.println(name + " はいろんなタイプに進化できる！");
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon poke1 = new Pikachu("ピカチュウ", 25); // アップキャスト
        Pokemon poke2 = new Eevee("イーブイ");

        if (poke1 instanceof Pikachu) {
            Pikachu pika = (Pikachu) poke1; // ダウンキャスト
            pika.thunderbolt();
        }

        switch (poke2) {
            case Pikachu p -> p.thunderbolt();
            case Eevee e -> e.adapt();
            default -> System.out.println("未知のポケモン");
        }
    }
}
```

🧩 これでポケモンの正体を見抜き、適切な技を使えるようになろう！

---

# 🎭 第9章 一つの技で多様な効果！ポリモーフィズム（多態性）

## 💡 9.1 オーバーロード

### 🧠 「同じ技の名前で別の効果」オーバーロードの仕組み

Javaでは、**同じメソッド名で引数の数や型が違えば別のメソッドとして扱える**、これがオーバーロードです。  
まるで「たいあたり（通常）」と「たいあたり（ダブルバトル）」のような違い！

```java
public void attack(String move) {
    System.out.println("「" + move + "」を使った！");
}

public void attack(String move, int times) {
    System.out.println("「" + move + "」を" + times + "回連続で使った！");
}
```

📝 同じ名前のメソッドを、**異なる形で使い分ける**ことができるのがオーバーロードの特徴です。

---

## 🔁 9.2 オーバーライド

### 🔄 「進化して技が強化された！」オーバーライドの本質

オーバーライドは、**親クラスのメソッドを子クラスで書き換える**ことです。  
たとえば、同じ「attack()」でも進化後はもっと強力にしたい！

```java
public class Pokemon {
    public void attack() {
        System.out.println("ノーマルアタック！");
    }
}

public class Pikachu extends Pokemon {
    @Override
    public void attack() {
        System.out.println("ピカチュウの10まんボルト！");
    }
}
```

📝 `@Override`は、**ちゃんとオーバーライドできているかをチェックするアノテーション**です。

---

## 🌀 9.3 ポリモーフィズム（多態性）

### 🎨 「一つの技名で違う効果」ポリモーフィズムのすごさ

**ポリモーフィズム（多態性）**とは、**親クラスの型で、子クラスのメソッドが実行される**しくみです。

```java
Pokemon poke1 = new Pikachu(); // 親クラスの変数
poke1.attack(); // 実行時にはPikachuのattack()が使われる
```

📝 呼び出すときの型ではなく、**実際の中身の型（インスタンス）**でメソッドが決まります。  
これを「動的バインディング」といいます。

---

### ✨️独自仕様：トレーナーによって異なる演出を加える例

```java
public class Trainer {
    public void usePokemon(Pokemon p) {
        p.attack(); // 実際の種類に応じた攻撃を実行
    }
}
```

ポケモンが何か分からなくても、**共通のインターフェースで呼び出せる**便利さがポリモーフィズムです。

---

## 🎯 9.4 まとめとテスト

### ✅ ポリモーフィズムのまとめ表

| 概念 | 説明 |
|------|------|
| オーバーロード | 同じ名前でも引数違いで使える |
| オーバーライド | 親クラスのメソッドを書き換える |
| ポリモーフィズム | 親型で子の処理を実行できる仕組み |
| 動的バインディング | 実行時に正しいメソッドを呼ぶ |

---

### 💻 総合サンプルコード

```java
public class Pokemon {
    public void attack() {
        System.out.println("ノーマルアタック！");
    }

    public void attack(String move) {
        System.out.println("「" + move + "」を使った！");
    }

    public void attack(String move, int times) {
        System.out.println("「" + move + "」を" + times + "回使った！");
    }
}

class Pikachu extends Pokemon {
    @Override
    public void attack() {
        System.out.println("ピカチュウの10まんボルト！");
    }
}

class Eevee extends Pokemon {
    @Override
    public void attack() {
        System.out.println("イーブイのスピードスター！");
    }
}

class Trainer {
    public void usePokemon(Pokemon p) {
        p.attack(); // ポリモーフィズムにより正しい技が使われる
    }
}

public class Main {
    public static void main(String[] args) {
        Trainer ash = new Trainer();

        Pokemon pika = new Pikachu();
        Pokemon eevee = new Eevee();

        ash.usePokemon(pika);   // ピカチュウの技
        ash.usePokemon(eevee);  // イーブイの技

        pika.attack("アイアンテール");        // オーバーロード（1）
        pika.attack("でんこうせっか", 2);     // オーバーロード（2）
    }
}
```

🧩 このコードで、**オーバーロード・オーバーライド・ポリモーフィズム**の全てを体験できます！

---

# 🦄 第10章 幻のポケモンの謎！抽象クラスの世界

## 🧩 10.1 抽象クラスとは

### 👻 「図鑑に載っていない謎のポケモン」抽象クラスの特徴と役割

抽象クラス（abstract class）は、**「不完全な設計図」**のようなもの。  
直接インスタンス化はできず、**サブクラスで完成させてから使う**必要があります。

```java
public abstract class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("私は " + name + "！タイプは " + type + "！");
    }

    public abstract void specialMove(); // 抽象メソッド：中身がない
}
```

📝 `abstract`がついたメソッドには処理が書けません。**サブクラスが実装を引き継ぐ前提**です。

---

## 🧬 10.2 抽象クラスを継承する

### 🌟 「幻から実在へ」抽象メソッドの実装テクニック

抽象クラスを継承すると、**abstractメソッドを必ず実装**しなければなりません。

```java
public class Mew extends Pokemon {
    public Mew() {
        name = "ミュウ";
        type = "エスパー";
    }

    @Override
    public void specialMove() {
        System.out.println("ミュウのサイコキネシス！");
    }
}
```

📝 このように、`specialMove()`の中身を**具象クラス（子クラス）で必ず記述**します。

---

### ✨️独自仕様：「半分だけ実在する？」サブクラスも抽象クラスにする方法

```java
public abstract class LegendaryPokemon extends Pokemon {
    public abstract void summon(); // さらに抽象化された動作
}
```

📝 中間クラスで**さらに抽象的な定義を追加**することも可能です。

---

## 🗺 10.3 抽象クラスのクラス図

### 🖼 「幻のポケモンも図鑑に載せる」抽象クラスの表記法

以下は簡単なクラス図イメージです：

```
<<abstract>> Pokemon
    +introduce()
    +specialMove() ← abstract

        ▲
        |
   Mew  : implements specialMove()
```

📝 `<<abstract>>` は抽象クラスを意味し、**三角矢印は継承**を表します。

---

## 🎯 10.4 まとめとテスト

### ✅ 抽象クラスのまとめ表

| 項目 | 内容 |
|------|------|
| abstract class | 不完全な設計図、直接インスタンス化できない |
| abstract method | 中身のないメソッド。子クラスで定義が必要 |
| 継承強制 | 抽象メソッドがあると、継承先で必ずオーバーライド |
| 中間抽象化 | 抽象クラス同士の継承も可能 |

---

### 💻 総合サンプルコード

```java
public abstract class Pokemon {
    protected String name;
    protected String type;

    public void introduce() {
        System.out.println("私は " + name + "、タイプは " + type + " です！");
    }

    public abstract void specialMove(); // 抽象メソッド
}

class Mew extends Pokemon {
    public Mew() {
        this.name = "ミュウ";
        this.type = "エスパー";
    }

    @Override
    public void specialMove() {
        System.out.println(name + "のサイコキネシス！");
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon mystery = new Mew(); // 抽象クラスの型でインスタンスを扱う
        mystery.introduce();         // 実装済みのメソッド
        mystery.specialMove();       // オーバーライドされたメソッド
    }
}
```

🧩 このコードでは、**抽象クラスの利用・オーバーライド・ポリモーフィズム**を体験できます！


---

# 🔗 第11章 ポケモンのタイプと能力！インタフェースの力

## 💡 11.1 インタフェースとは

### 🔍 「ひこうタイプ」「みずタイプ」インタフェースの定義と本質

Javaの**インタフェース（interface）**は、「ポケモンのタイプ」のようなものです。  
同じ技を使える能力を複数のポケモンが共有することができます。

```java
public interface Flyable {
    void fly(); // ひこうタイプなら必ず飛べるようにする
}
```

📝 `interface`は**機能の契約書**のようなもので、中身のないメソッドだけ定義します。

---

### 🧪 「複数のタイプを持つポケモン」クラスへのインタフェース実装

```java
public class Charizard implements Flyable {
    @Override
    public void fly() {
        System.out.println("リザードンは空を飛んだ！");
    }
}
```

📝 `implements`を使って、「このポケモンは飛べる」と明示的に宣言しています。

---

### ✨️独自仕様：「誰も変えられない特性」封印されたインタフェースの謎

インタフェースのメソッドはすべて`public abstract`です。変更できません。  
この特性が、**共通の技を誰でも同じように使わせるためのルール**を保っています。

---

## 🔁 11.2 インタフェース型への型変換

### 🔄 「タイプとしてのポケモン」インタフェース型の正体

```java
Flyable flyingPokemon = new Charizard();
flyingPokemon.fly(); // リザードンのfly()が実行される
```

📝 インタフェース型の変数でオブジェクトを扱うことで、**タイプに応じた共通操作**が可能になります。

---

### 🎯 「みずタイプとして扱う」インタフェース型への変換テクニック

```java
public interface WaterType {
    void surf();
}

public class Vaporeon implements WaterType {
    @Override
    public void surf() {
        System.out.println("シャワーズのなみのり！");
    }
}
```

WaterType v = new Vaporeon(); のように使えます。

---

## 🎭 11.3 インタフェースによるポリモーフィズム

### 🧬 「タイプが違っても同じ技名」インタフェースで実現する多態性

```java
public void useFly(Flyable f) {
    f.fly(); // Flyableなら誰でも飛べる
}
```

📝 インタフェースを使えば、**クラスに関係なく同じ機能を実行**できます。

---

### 🧪 「実践！タイプ別技エフェクト」インタフェースの活用術

```java
Flyable f1 = new Charizard();
Flyable f2 = new Pidgeot();

f1.fly(); // リザードン
f2.fly(); // ピジョット
```

クラスが違っても、**fly()という共通の動作を使える**のが強みです。

---

## 🌐 11.4 インタフェースの継承

### 🔗 「特殊なタイプの誕生」インタフェース同士の継承の不思議

```java
public interface FlyingWaterType extends Flyable, WaterType {
    void dive();
}
```

📝 こうして「ひこう + みず」両方の能力をもった**特殊なタイプ**を作ることもできます。

---

### 🧠 「進化しても受け継がれるタイプ」サブクラスに継承されるインタフェース

```java
public class Gyarados implements FlyingWaterType {
    @Override
    public void fly() {
        System.out.println("ギャラドスが舞い上がった！");
    }

    @Override
    public void surf() {
        System.out.println("ギャラドスのなみのり！");
    }

    @Override
    public void dive() {
        System.out.println("ギャラドスが深海に潜った！");
    }
}
```

---

## 🎯 11.5 まとめとテスト

### ✅ インタフェースのまとめ表

| 項目 | 説明 |
|------|------|
| interface | 機能の契約、タイプのようなもの |
| implements | インタフェースの機能を実装する |
| 多重実装 | 複数のタイプを同時に持つことが可能 |
| ポリモーフィズム | クラスに関係なく共通操作が可能 |

---

### 💻 総合サンプルコード

```java
public interface Flyable {
    void fly();
}

public interface WaterType {
    void surf();
}

public class Charizard implements Flyable {
    @Override
    public void fly() {
        System.out.println("リザードンが空を飛んだ！");
    }
}

public class Vaporeon implements WaterType {
    @Override
    public void surf() {
        System.out.println("シャワーズがなみのりを使った！");
    }
}

public class Gyarados implements Flyable, WaterType {
    @Override
    public void fly() {
        System.out.println("ギャラドスが舞い上がった！");
    }

    @Override
    public void surf() {
        System.out.println("ギャラドスがなみのりを繰り出した！");
    }
}

public class Main {
    public static void main(String[] args) {
        Flyable f = new Charizard();
        WaterType w = new Vaporeon();
        Flyable fw = new Gyarados();

        f.fly();
        w.surf();
        fw.fly();

        if (fw instanceof WaterType water) {
            water.surf(); // Gyaradosとしてsurfも使える
        }
    }
}
```

🧩 この章では、「複数タイプ」「共通技」「型変換」など**Javaのインタフェースのすべて**が学べます！

---

