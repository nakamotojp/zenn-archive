---
title: Javaメソッドが意味不明だったので、ポケモンとレジで覚えたら最強だった【マイクラModにも役立つ】
tags: Java入門 メソッド ポケモン マイクラ 小学生
author: nakamoto
slide: false
---

# 🔍 逆引きメソッド目次【Java × ポケモン × コンビニ】

🔹 [第1章 Javaのメソッドを学ぼう！〜ポケモンとコンビニで基礎理解〜](#第1章-javaのメソッドを学ぼうポケモンとコンビニで基礎理解)
🔹 [1.1 メソッドとは？](#11-メソッドとは)
🔹 [1.2 ポケモンの例：こうげきメソッド](#12-ポケモンの例こうげきメソッド)
🔹 [1.3 コンビニの例：レジでお礼を言う](#13-コンビニの例レジでお礼を言う)

🔹 [第2章 戻り値がvoid（なし）のメソッド活用法](#第2章-戻り値がvoidなしのメソッド活用法)
🔹 [2.1 voidメソッドとは？](#21-voidメソッドとは)
🔹 [2.2 ポケモンの例：メッセージだけ表示するメソッド](#22-ポケモンの例メッセージだけ表示するメソッド)
🔹 [2.3 コンビニの例：レシートメッセージを表示するだけ](#23-コンビニの例レシートメッセージを表示するだけ)

🔹 [第3章 引数と戻り値ありのメソッドを学ぼう！](#第3章-引数と戻り値ありのメソッドを学ぼう)
🔹 [3.1 ポケモンの例：ダメージ計算メソッド](#31-ポケモンの例ダメージ計算メソッド)
🔹 [3.2 コンビニの例：おつりの金額を計算して返す](#32-コンビニの例おつりの金額を計算して返す)

🔹 [第4章 引数と戻り値：別の角度からの例で理解を深めよう！](#第4章-引数と戻り値別の角度からの例で理解を深めよう)
🔹 [4.1 ポケモンの例：相性によるメッセージを返すメソッド](#41-ポケモンの例相性によるメッセージを返すメソッド)
🔹 [4.2 コンビニの例：支払いが十分かを判定するメソッド（boolean型）](#42-コンビニの例支払いが十分かを判定するメソッドboolean型)

🔹 [第5章 ステップバイステップで学ぶ：メソッド連携バトルシミュレーション](#第5章-ステップバイステップで学ぶメソッド連携バトルシミュレーション)
🔹 [5.1 ポケモンの例：こうげき＋相性＋結果表示の総合演出](#51-ポケモンの例こうげき相性結果表示の総合演出)
🔹 [5.2 コンビニの例：おつり計算＋レシート印刷の連携処理](#52-コンビニの例おつり計算レシート印刷の連携処理)

🔹 [第6章 データ型を活用したメソッドの実践編（long, double, boolean）](#第6章-データ型を活用したメソッドの実践編long-double-boolean)
🔹 [6.1 ポケモンの例：累計経験値・平均レベル・進化判定](#61-ポケモンの例累計経験値平均レベル進化判定)
🔹 [6.2 コンビニの例：年間売上・平均支払額・レジ袋の有無](#62-コンビニの例年間売上平均支払額レジ袋の有無)

🔹 [第7章 オーバーロード（同じ名前で使い分ける）メソッド【上級用】](#第7章-オーバーロード同じ名前で使い分けるメソッド上級用)
🔹 [7.1 ポケモンの例：技あり／技なしで分ける攻撃メソッド](#71-ポケモンの例技あり技なしで分ける攻撃メソッド)
🔹 [7.2 コンビニの例：注文内容に応じた order() メソッド](#72-コンビニの例注文内容に応じた-order-メソッド)

🔹 [第8章 戻り値あり・なしの使い分け 練習問題集](#第8章-戻り値ありなしの使い分け-練習問題集)
🔹 [練習：ポケモンのこうげき／ダメージ計算](#練習ポケモンのこうげきダメージ計算)
🔹 [練習：おつり／お礼表示／支払い判定](#練習おつりお礼表示支払い判定)

---

# 🧩 第1章 Javaのメソッドを学ぼう！〜ポケモンとコンビニで基礎理解〜

## 🎯 この章のゴール

- 「メソッドとは何か？」をイメージで理解できるようになる
- ポケモンやコンビニの例を通して、基本的なメソッドの形を体験する
- Javaのメソッド定義と呼び出しの構文に慣れる

---

## 1.1 メソッドとは？

メソッドとは、「ある処理のまとまりに名前をつけたもの」です。  
ポケモンでいうと、「こうげき！」というアクション。  
コンビニでいえば、「レジで“ありがとうございました”を言う」アクション。

### 🧠 なぜメソッドを使うの？
- 何度も同じ処理を書くのは大変だから
- 名前をつけることで、何をしているかが分かりやすくなるから
- プログラムが整理されて見やすくなるから

---

## 1.2 ポケモンの例：こうげきメソッド

```java
public class Pokemon {

    // attackメソッド（戻り値なし、引数なし）：固定のメッセージを表示する
    public static void attack() {
        System.out.println("ピカチュウ の こうげき！");
        System.out.println("ピカチュウ は たいあたり を くりだした！");
    }

    public static void main(String[] args) {
        attack();  // attackメソッドを呼び出す
    }
}
```

### 🪜 ステップ解説

1. `public static void attack()`：名前が `attack` のメソッドを定義（void = 戻り値なし）
2. `System.out.println(...)`：文字を画面に表示する命令
3. `main` メソッドから `attack()` を呼び出すことで、上の2行が表示される

---

## 1.3 コンビニの例：レジでお礼を言う

```java
public class Register {

    // sayThanksメソッド：表示するだけの簡単な処理
    public static void sayThanks() {
        System.out.println("ありがとうございました。またお越しくださいませ！");
    }

    public static void main(String[] args) {
        sayThanks();  // メソッドを呼び出すことで、メッセージを表示
    }
}
```

### 🪜 ステップ解説

1. `sayThanks()` は「お礼を言う」だけの動作
2. 引数も戻り値もなく、画面にメッセージを出すだけ
3. レジでボタンを押したら音声が出るようなイメージ

---

## ✅ この章のまとめ

| 覚えること | 内容 |
|------------|------|
| メソッドとは | 処理に名前をつけて、何度でも使えるようにするしくみ |
| void型 | 戻り値がないメソッドにつける |
| 呼び出し方 | `メソッド名();` で呼び出すことができる |

---

次章では、`void` ではなく「**結果を返すメソッド**」を学びます！

---

# 🚫 第2章 戻り値がvoid（なし）のメソッド活用法

## 🎯 この章のゴール

- `void`（戻り値なし）のメソッドとは何かを理解する
- 「表示だけする」「処理だけする」メソッドの使いどころを学ぶ
- ポケモンとコンビニの例で「返さない処理」のイメージを持つ

---

## 2.1 voidメソッドとは？

Javaのメソッドには「戻り値」があるものとないものがあります。  
`void`は「戻り値がないメソッド」を表します。  
つまり、**何か処理はするけど、値を返す必要がないときに使います。**

---

## 2.2 ポケモンの例：メッセージだけ表示するメソッド

```java
public class PokemonBattle {

    // attackMessageメソッド：ポケモンと技名を受け取ってメッセージを表示する
    public static void attackMessage(String name, String move) {
        System.out.println(name + " の こうげき！");
        System.out.println(name + " は " + move + " を くりだした！");
    }

    public static void main(String[] args) {
        attackMessage("ピカチュウ", "10まんボルト");  // 表示だけして値は返さない
    }
}
```

### 🪜 ステップ解説

1. `void`型を使って戻り値がないメソッドを定義している
2. 引数としてポケモン名と技名を受け取り、メッセージを表示するだけ
3. 値を返す必要がないので、呼び出しても変数に代入する必要なし

---

## 2.3 コンビニの例：レシートメッセージを表示するだけ

```java
public class Receipt {

    // printReceiptメソッド：商品名と合計金額を受け取ってレシート風メッセージを出す
    public static void printReceipt(String item, int price) {
        System.out.println("📄 レシート");
        System.out.println("商品: " + item);
        System.out.println("合計金額: " + price + " 円");
        System.out.println("ご利用ありがとうございました！");
    }

    public static void main(String[] args) {
        printReceipt("チョコレート", 150);  // 表示だけして終了
    }
}
```

### 🪜 ステップ解説

1. `printReceipt`メソッドは、表示のためだけのメソッド
2. `item`と`price`を受け取り、メッセージとして出力
3. `void`だから何も返さないし、他の処理に使う値もない

---

## ✅ この章のまとめ

| 用語 | 内容 |
|------|------|
| void型 | 戻り値なし。処理だけして終了する |
| 主な用途 | メッセージ表示、通知、音、ファイル保存など |
| ポイント | 「結果として値がいらない処理」のときに選ぶ |

---

次章では、**値を受け取り、結果を返すメソッド（戻り値あり）**を学びます！

---

# 🔁 第3章 引数と戻り値ありのメソッドを学ぼう！

## 🎯 この章のゴール

- 「引数」と「戻り値」の意味と役割を理解する
- 計算結果などを「返す」処理の基本パターンを身につける
- ポケモンとコンビニの例を通して、数値の計算と活用を学ぶ

---

## 3.1 ポケモンの例：ダメージ計算メソッド

```java
public class Battle {

    // calculateDamageメソッド：
    // こうげき力とぼうぎょ力を受け取り、ダメージを計算して返す
    public static int calculateDamage(int power, int defense) {
        int damage = power - (defense / 2);
        return damage;
    }

    public static void main(String[] args) {
        int attackPower = 50;
        int enemyDefense = 20;

        int resultDamage = calculateDamage(attackPower, enemyDefense);  // 戻り値を受け取る
        System.out.println("こうげきのダメージは " + resultDamage + " です！");
    }
}
```

### 🪜 ステップ解説

1. メソッドの戻り値の型は `int` → 数値を返す
2. 引数として攻撃力と防御力を渡す
3. 計算結果（ダメージ）を `return` で呼び出し元へ返す
4. 呼び出した側は `int resultDamage = ...` で受け取って利用

---

## 3.2 コンビニの例：おつりの金額を計算して返す

```java
public class ChangeCalculator {

    // calculateChangeメソッド：
    // 支払い金額と商品価格を受け取り、おつりを返す
    public static int calculateChange(int paid, int price) {
        int change = paid - price;
        return change;
    }

    public static void main(String[] args) {
        int paidMoney = 1000;
        int itemPrice = 620;

        int change = calculateChange(paidMoney, itemPrice);  // 戻り値を受け取る
        System.out.println("おつりは " + change + " 円です！");
    }
}
```

### 🪜 ステップ解説

1. 支払い金額と価格を引数で受け取る
2. 差分を計算して `int` 型の戻り値として返す
3. 結果は変数に代入し、画面に表示する

---

## ✅ この章のまとめ

| 用語 | 内容 |
|------|------|
| 引数 | メソッドに「外から渡す値」 |
| 戻り値 | メソッドが「返す計算結果など」 |
| return文 | 処理の結果を返すときに使うキーワード |

---

次章では、**文字列や条件によって変わる戻り値のパターン**を学びます！


---

# 🔄 第4章 引数と戻り値：別の角度からの例で理解を深めよう！

## 🎯 この章のゴール

- 数値だけでなく文字列や真偽値の戻り値も扱えることを知る
- 条件によって戻す結果が変わる処理を学ぶ
- ポケモンとコンビニの視点で、メソッドの表現力を広げる

---

## 4.1 ポケモンの例：相性によるメッセージを返すメソッド

```java
public class TypeChecker {

    // getEffectivenessメソッド：タイプ相性を判定し、文字列で返す
    public static String getEffectiveness(String attackType, String enemyType) {
        if (attackType.equals("でんき") && enemyType.equals("みず")) {
            return "こうかはばつぐんだ！";
        } else if (attackType.equals("でんき") && enemyType.equals("じめん")) {
            return "こうかがないようだ…";
        } else {
            return "ふつうのこうかだ。";
        }
    }

    public static void main(String[] args) {
        String result = getEffectiveness("でんき", "みず");  // 戻り値を受け取る
        System.out.println("判定結果: " + result);
    }
}
```

### 🪜 ステップ解説

1. 引数で攻撃と相手のタイプを受け取る
2. 条件分岐に応じて文字列を選んで返す
3. 呼び出し側は結果を文字列変数に受け取って表示する

---

## 4.2 コンビニの例：支払いが十分かを判定するメソッド（boolean型）

```java
public class PaymentChecker {

    // isEnoughPaymentメソッド：支払いが価格以上ならtrue、そうでなければfalseを返す
    public static boolean isEnoughPayment(int paid, int price) {
        return paid >= price;
    }

    public static void main(String[] args) {
        boolean result = isEnoughPayment(500, 400);  // 真偽値を受け取る
        if (result) {
            System.out.println("支払いOKです！");
        } else {
            System.out.println("金額が足りません！");
        }
    }
}
```

### 🪜 ステップ解説

1. 比較の結果（true/false）を返す
2. 呼び出し元で `if` 文と組み合わせて使える
3. 条件判定の基本構造を理解するのにぴったり

---

## ✅ この章のまとめ

| 型 | 用途 | 例 |
|----|------|----|
| `String` | メッセージや分類結果を返す | タイプ相性、商品名など |
| `boolean` | 条件に基づく結果（真/偽） | 十分な支払いか？など |
| `if` と連携 | 戻り値を使って処理を分ける | `if (isOK)` のように使う |

---

次章では、**複数のメソッドを組み合わせて一連の処理を完成させる方法**を学びます！


---

# 📘 第5章 ステップバイステップで学ぶ：メソッド連携バトルシミュレーション

## 🎯 この章のゴール

- 複数のメソッドを連携させて、ひとまとまりの処理を完成させる
- 「設計 → 分解 → 呼び出し」の流れを身につける
- ポケモンのバトル演出と、コンビニの支払い処理で体験的に学ぶ

---

## 5.1 ポケモンの例：こうげき＋相性＋結果表示の総合演出

```java
public class AttackSystem {

    // ダメージを計算するメソッド
    public static int calculateDamage(int power, int defense) {
        int damage = power - (defense / 2);
        return damage;
    }

    // 相性メッセージを返すメソッド
    public static String getEffectiveness(String attackType, String enemyType) {
        if (attackType.equals("でんき") && enemyType.equals("みず")) {
            return "こうかはばつぐんだ！";
        } else if (attackType.equals("でんき") && enemyType.equals("じめん")) {
            return "こうかがないようだ…";
        } else {
            return "ふつうのこうかだ。";
        }
    }

    // 総合結果を表示するメソッド
    public static void showAttackResult(String name, int power, int defense, String attackType, String enemyType) {
        int damage = calculateDamage(power, defense);
        String message = getEffectiveness(attackType, enemyType);

        System.out.println(name + " のこうげき！");
        System.out.println("ダメージは " + damage + " です！");
        System.out.println("相性：" + message);
    }

    public static void main(String[] args) {
        showAttackResult("ピカチュウ", 50, 20, "でんき", "みず");
    }
}
```

### 🪜 ステップ解説

1. 「ダメージ計算」と「相性判定」の2つの処理を用意
2. それぞれを分けたメソッドにして、再利用性を高める
3. 表示を担当するメソッドが、他のメソッドを内部で呼び出す

---

## 5.2 コンビニの例：おつり計算＋レシート印刷の連携処理

```java
public class ReceiptSystem {

    // おつりを計算するメソッド
    public static int calculateChange(int paid, int price) {
        return paid - price;
    }

    // レシートを表示するメソッド
    public static void printReceipt(String item, int paid, int price) {
        int change = calculateChange(paid, price);

        System.out.println("📄 レシート");
        System.out.println("商品: " + item);
        System.out.println("支払額: " + paid + " 円");
        System.out.println("商品価格: " + price + " 円");
        System.out.println("おつり: " + change + " 円");
        System.out.println("ありがとうございました！");
    }

    public static void main(String[] args) {
        printReceipt("おにぎり", 500, 130);
    }
}
```

### 🪜 ステップ解説

1. `calculateChange` はおつりを計算するだけのメソッド
2. `printReceipt` はレシート印刷用の表示処理
3. `printReceipt` の中で `calculateChange` を呼び出している

---

## ✅ この章のまとめ

| ポイント | 内容 |
|----------|------|
| メソッドの分割 | 複数の処理を分けて、読みやすく・再利用しやすく |
| 呼び出し構造 | メソッドの中から他のメソッドを使える |
| 表現力UP | 複雑な処理でも整理して書けるようになる |

---

次章では、**さまざまなデータ型（long, double, boolean）を使った応用処理**を学びます！


---

# 🔣 第6章 データ型を活用したメソッドの実践編（long, double, boolean）

## 🎯 この章のゴール

- Javaの代表的なデータ型（long, double, boolean）を使い分ける
- 型に応じて適切なメソッドの書き方と用途を学ぶ
- ポケモンとコンビニの例を通して、応用的な型の使い方を理解する

---

## 6.1 long型：とても大きな数値を扱う

### 🎮 ポケモンの例：累計経験値を計算する

```java
public class ExperienceCalculator {

    // 経験値を累計するlong型メソッド
    public static long calculateTotalExperience(long baseExp, long bonusExp) {
        return baseExp + bonusExp;
    }

    public static void main(String[] args) {
        long base = 950000000L;
        long bonus = 40000000L;

        long total = calculateTotalExperience(base, bonus);
        System.out.println("累計経験値: " + total + " XP");
    }
}
```

### 🪜 ステップ解説

1. `long` 型は `int` より大きな数を扱える（L をつけて明示）
2. 引数で2つの経験値を受け取り、合計を返す
3. 戻り値も `long` 型として受け取り、表示する

---

### 🏪 コンビニの例：年間売上の合計を出す

```java
public class SalesCalculator {

    public static long calculateAnnualSales(long janToNov, long december) {
        return janToNov + december;
    }

    public static void main(String[] args) {
        long firstElevenMonths = 1250000000L;
        long decemberSales = 250000000L;

        long total = calculateAnnualSales(firstElevenMonths, decemberSales);
        System.out.println("年間売上: " + total + " 円");
    }
}
```

---

## 6.2 double型：小数点を含む数値を扱う

### 🎮 ポケモンの例：平均レベルを求める

```java
public class LevelAnalyzer {

    public static double calculateAverageLevel(double level1, double level2) {
        return (level1 + level2) / 2;
    }

    public static void main(String[] args) {
        double avg = calculateAverageLevel(23.5, 36.5);
        System.out.println("平均レベル: " + avg);
    }
}
```

---

### 🏪 コンビニの例：支払いの平均金額を出す

```java
public class AveragePayment {

    public static double calculateAveragePayment(double total1, double total2) {
        return (total1 + total2) / 2;
    }

    public static void main(String[] args) {
        double result = calculateAveragePayment(520.5, 479.5);
        System.out.println("平均支払い金額: " + result + " 円");
    }
}
```

---

## 6.3 boolean型：条件を満たしているかを判断する

### 🎮 ポケモンの例：レベルが進化に達しているか判定する

```java
public class EvolutionChecker {

    public static boolean canEvolve(int level) {
        return level >= 16;
    }

    public static void main(String[] args) {
        boolean result = canEvolve(20);
        System.out.println(result ? "進化できます！" : "まだ進化できません。");
    }
}
```

---

### 🏪 コンビニの例：レジ袋が必要かを判定する

```java
public class BagChecker {

    public static boolean needsBag(int itemCount) {
        return itemCount > 3;
    }

    public static void main(String[] args) {
        boolean result = needsBag(5);
        System.out.println(result ? "レジ袋をつけましょう。" : "レジ袋は不要です。");
    }
}
```

---

## ✅ この章のまとめ

| データ型 | 用途例 | 使いどころ |
|----------|--------|------------|
| `long` | 巨大な数値（経験値・売上） | intでは足りないとき |
| `double` | 小数（平均など） | より正確な計算に |
| `boolean` | はい/いいえの判定 | 条件に応じた処理分岐 |

---

次章では、**メソッド名が同じでも引数によって処理を切り替える「オーバーロード」**を学びます！

---

# 🧠【上級用】第7章 オーバーロード（同じ名前で使い分ける）メソッド

> 🧠 上級編の内容ですが、「同じ名前のメソッドで何ができるのか？」の仕組みを知ることで、プログラミングの表現力がぐんと上がります！

## 🎯 この章のゴール

- 「オーバーロード（Overload）」の概念を理解する
- 同じ名前のメソッドで、引数の違いに応じて処理を切り替える方法を学ぶ
- ポケモンとコンビニの例で柔軟なメソッド設計に触れる

---

## 7.1 ポケモンの例：技あり／技なしで分ける攻撃メソッド

```java
public class OverloadExample {

    // attackメソッド①：名前だけで攻撃メッセージを表示
    public static void attack(String name) {
        System.out.println(name + " が こうげきした！");
    }

    // attackメソッド②：名前と技を指定して表示
    public static void attack(String name, String move) {
        System.out.println(name + " は " + move + " を くりだした！");
    }

    public static void main(String[] args) {
        attack("ピカチュウ");  // 技なし
        attack("リザードン", "かえんほうしゃ");  // 技あり
    }
}
```

### 🪜 ステップ解説

1. 同じメソッド名 `attack` を使っている
2. 引数の数が違う（1つ／2つ）ことで別のメソッドと認識される
3. 呼び出すときに、渡す引数の数で適切な処理が選ばれる

---

## 7.2 コンビニの例：注文時のオプション指定

```java
public class Cafe {

    // orderメソッド①：何も指定しない場合
    public static void order() {
        System.out.println("ホットコーヒーを1つお願いします！");
    }

    // orderメソッド②：飲み物を指定
    public static void order(String drink) {
        System.out.println(drink + " を1つお願いします！");
    }

    // orderメソッド③：飲み物とサイズを指定
    public static void order(String drink, String size) {
        System.out.println(size + "サイズの " + drink + " をお願いします！");
    }

    public static void main(String[] args) {
        order();  // デフォルト注文
        order("アイスティー");  // 種類を指定
        order("カフェラテ", "L");  // 種類とサイズを指定
    }
}
```

### 🪜 ステップ解説

1. `order()` は引数のパターンごとに3種類存在
2. メソッド名は同じでも、渡す引数の数と型で動作が分かれる
3. 呼び出し側は、目的に応じた形で使い分けられる

---

## ✅ この章のまとめ

| 用語 | 内容 |
|------|------|
| オーバーロード | 同じ名前のメソッドを、引数の違いで使い分けるしくみ |
| メリット | 名前を統一しながら複数のパターンに対応できる |
| 注意点 | 引数の「型」や「数」が違わないと区別できない |

---

次章では、**「返す？返さない？」を見極めてメソッドを選べるようになる練習問題**を通して理解を深めます！

---

# 📚 第8章 戻り値あり・なしの使い分け 練習問題集

## 🎯 この章のゴール

- 処理の目的に応じて、「戻り値あり or なし（void）」を適切に選べるようになる
- どのようなときに値を返す必要があるかを判断できる
- ポケモンバトルとコンビニのレジを題材に、判断力を養う

---

## 🔁 練習問題：ポケモン編

### 問1：技を表示するだけのメソッド

#### 要求
- ポケモン名と技名を受け取って、こうげきのメッセージを表示するだけのメソッドを作ってください。

#### ヒント
- 表示だけなら **戻り値は不要**
- `void` を使う

---

### 問2：ダメージを計算して返すメソッド

#### 要求
- こうげき力とぼうぎょ力を受け取り、ダメージを数値で返すメソッドを作ってください。

#### ヒント
- 計算結果を返すには **戻り値が必要**
- 戻り値の型は `int`

---

## 🏪 練習問題：コンビニのレジ編

### 問3：おつりを計算して返すメソッド

#### 要求
- 支払い金額と商品価格を受け取り、おつりを `int` 型で返してください。

#### ヒント
- 金額の「差」を返すなら、戻り値は必要

---

### 問4：お礼を言うメッセージを表示するだけのメソッド

#### 要求
- 「ありがとうございました！」を画面に表示するだけのメソッドを作ってください。

#### ヒント
- 表示だけ → 戻り値は不要 → `void`

---

### 問5：支払いが足りているかを真偽値で返すメソッド

#### 要求
- 支払い金額と価格を受け取り、`true` または `false` を返すメソッドを作ってください。

#### ヒント
- `boolean` 型を戻す
- `return paid >= price;` のように使える

---

## ✅ この章のまとめ

| 処理の目的 | 戻り値の有無 | 適した型 |
|-------------|----------------|-------------|
| 表示だけ | なし（`void`） | - |
| 計算して渡す | あり | `int`, `double`, `String`など |
| 条件判定 | あり | `boolean` |

---

この章を通して、「**このメソッド、返す必要ある？**」という視点を持てるようになれば、メソッド設計力が確実にレベルアップしています！

---
