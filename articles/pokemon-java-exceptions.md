---
title: 「中学生でもわかるポケモンで完全理解！Javaの例外処理11選：ピカチュウがコードも出力もぜんぶ見せるからNullも配列ミスも怖くない」
tags: Java入門 例外処理 ポケモン 中学生
author: nakamoto
slide: false
---

# 💥Javaの例外処理をポケモンで学ぼう！

プログラムには、**予想外のトラブル**が起きることがあります。
Javaではそのような「問題が起きたとき」に、プログラムが止まらないように\*\*例外処理（Exception Handling）\*\*を使います。

今回は、ポケモンの世界と実生活を使って、楽しく学んでみましょう！

## 🔎 逆引き目次（ジャンプリンク付き）

- [例外が発生する理由](#1️⃣-例外が発生する理由)
- [一般的な例外処理とは？](#2️⃣-一般的な例外処理とは)
- [Javaの代表的な例外処理メソッドと利用シーン](#3️⃣-javaの代表的な例外処理メソッドと利用シーン)
- [代表メソッド5つ使ったコード例](#💻代表メソッド5つ使ったコード例)
- [例1：ピカチュウの技が出せない（Exception）](#🟡-例1ピカチュウの技が出せないポケモンの例)
- [例2：財布にお金が入っていない（Exception）](#🏠-例2財布にお金が入っていない実生活の例)
- [例3：ポケモンがいない場所を見ようとした（ArrayIndexOutOfBoundsException）](#🔴-例3ポケモンがいない場所を見ようとしたarrayindexoutofboundsexception)
- [例4：使うはずのお皿が無かった（NullPointerException）](#⚫-例4使うはずのお皿が無かった-nullpointerexception)
- [例5：ユーザー定義の例外（StaminaTooLowException）](#🔧-ユーザー定義の例外とは)
- [例6：複数のcatch文を使う（Multi-catch）](#🎭-複数のcatch文の使い分け)
- [例7：バトル後の回復は必ず（finally）](#🔚-例7finally-文-バトル後の回復タイム)
- [例8：ファイルを自動で閉じる（try-with-resources）](#📁-例8try-with-resources-ファイルを自動で閉じる)
- [例9：catchをまとめる・再スロー](#🪤-例9その他の応用テクニック)
- [例10：チェック例外 vs 非チェック例外](#⚖️-例10チェック例外-vs-非チェック例外runtim例外の違い)
- [例11：実務でのベストプラクティス](#💼-例11実務でのベストプラクティス)
- [Javaの代表的な例外クラス一覧（10選）](#📘-javaの代表的な例外クラス-一覧10選)
- [ポケモンで学ぶ！Javaの例外クラス10選（コード付き）](#🧪-ポケモンで学ぶjavaの例外クラス10選)


---

## 1️⃣ 例外が発生する理由

1. プログラム実装後コンパイルする
    2. コンパイルエラーが出れば、プログラムの修正が必要である
3. コンパイルエラーがでない場合でも、運用時に意図しない自体が発生する
    3. ここで例外処理が必要となる

--- 


## 2️⃣ 一般的な例外処理とは？
「例外（Exception）」とは、プログラム中に起こるエラーのこと。

たとえば：

1. 100(int:整数)ダメージ与えるつもりが、１００(String:文字列)ダメージ与えようとした
2. 存在しないポケモン(ファイル)にアクセスしようとした
3. 存在しない手持ちポケモン(配列のインデックス指定値)を取り出そうとした

こうした「異常な事態」に備えて、Javaでは「try-catch文」を使ってエラーを安全に処理できます。

``` java
try {
    // 問題が起こるかもしれない処理
} catch (例外の型 変数名) {
    // 問題が起こったときの処理
} finally {
    // 最後に必ず実行される処理
}
```

## 3️⃣ Javaの代表的な例外処理メソッドと利用シーン

| メソッド      | 役割               | 利用される場面例             |
| --------- | ---------------- | -------------------- |
| `try`     | エラーが起きそうな処理を書く   | ファイルを開く、配列アクセスなど     |
| `catch`   | エラーが起きたときの処理を書く  | ファイルが無い、数値の計算失敗など    |
| `finally` | 例外があっても必ず実行される処理 | ファイルを閉じる、メモリ解放など     |
| `throw`   | 例外を自分で発生させる      | 条件によってエラーを起こしたいとき    |
| `throws`  | メソッドでエラーが出ることを宣言 | エラーが発生する可能性のあるメソッド定義 |

## 💻代表メソッド5つ使ったコード例

``` java
public class PokemonCare {
    public static void main(String[] args) {
        try {
            // ポケモンのHPを回復する処理を実行（エラーが起こる可能性あり）
            healPokemon("ピカチュウ", 0);
        } catch (Exception e) {
            // エラーが起きたときの処理（例外をキャッチ）
            System.out.println("エラーが発生しました：" + e.getMessage());
        } finally {
            // 最後に必ず実行される処理
            System.out.println("回復処理を終了しました。");
        }
    }

    // throws：このメソッドは例外を投げるかもしれないよと宣言している
    public static void healPokemon(String name, int hp) throws Exception {
        // HPが0以下のときは回復できないので自分で例外を作ってthrow
        if (hp <= 0) {
            throw new Exception(name + " はひんし状態なので回復できません！");
        }

        // 通常の処理（今回はただの出力）
        System.out.println(name + " のHPが回復しました！");
    }
}

```

---

## 🟡 例１：ピカチュウの技が出せない（ポケモンの例）

### 🎮 ポケモンの状況

サトシがピカチュウに「10まんボルト」を出させようとしたけど、**PPがゼロで出せなかった！**

---

### 💻 Javaコードで書くと…

```java
public class PikachuBattle {
    public static void main(String[] args) {
        int pp = 0; // 技の残りPP（今回はゼロ）

        try {
            if (pp == 0) {
                throw new Exception("PPが足りません！");
            }

            System.out.println("ピカチュウの10まんボルト！こうかはばつぐんだ！");
        } catch (Exception e) {
            // エラーが出ても止まらず、代わりの行動をする
            System.out.println(e.getMessage());
            System.out.println("→ ピカチュウは代わりにたいあたりを使った！");
        }
    }
}
```

---

### 🖨 出力結果

```
PPが足りません！
→ ピカチュウは代わりにたいあたりを使った！
```

---

## 🏠 例２：財布にお金が入っていない（実生活の例）

### 🛒 状況

おにぎりを買おうとしたら、財布にお金がなかった！

---

### 💻 Javaコードで書くと…

```java
public class BuyOnigiri {
    public static void main(String[] args) {
        int money = 0; // 財布に入っているお金（今回はゼロ）

        try {
            if (money < 150) {
                throw new Exception("お金が足りません！");
            }

            System.out.println("おにぎりを買いました！");
        } catch (Exception e) {
            System.out.println(e.getMessage());
            System.out.println("→ 家にあるパンを食べることにしました。");
        }
    }
}
```

---

### 🖨 出力結果

```
お金が足りません！
→ 家にあるパンを食べることにしました。
```

---

## ✅ ここまでの例１－２ポイントまとめ

| 用語    | 内容                | 例                   |
| ----- | ----------------- | ------------------- |
| try   | 問題が起きるかもしれない処理を書く | 技を出す／買い物する          |
| throw | 自分で「例外（エラー）」を起こす  | PPが0のときに「技が出せない」と言う |
| catch | 問題が起きたときの対処方法を書く  | 代わりの技を出す／パンを食べる     |

---



## 🔴 例３：ポケモンがいない場所を見ようとした（ArrayIndexOutOfBoundsException）

### 🎮 ポケモンの状況

ポケモンボックスに3体しか入っていないのに、\*\*5番目（インデックス4）\*\*のポケモンを見ようとした！

---

### 💻 Javaコードで書くと…

```java
public class PokemonBox {
    public static void main(String[] args) {
        String[] box = {"ピカチュウ", "ヒトカゲ", "ゼニガメ"};

        try {
            // 存在しない5番目のポケモン（index 4）を見ようとする
            System.out.println("5番目のポケモン: " + box[4]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ボックスにそんなポケモンはいません！");
            System.out.println("→ 代わりに1番目のポケモンを見ます: " + box[0]);
        }
    }
}
```

---

### 🖨 出力結果

```
ボックスにそんなポケモンはいません！
→ 代わりに1番目のポケモンを見ます: ピカチュウ
```

---

## 🏠 実生活のたとえ：お弁当箱の4段目を探した（存在しない）

お弁当箱は3段しかないのに、4段目のふたを開けようとして怒られた！

---

---

## ⚫ 例４：使うはずのお皿が無かった（NullPointerException）

### 🎮 ポケモンの状況

バトル用の「どうぐ」を使おうとしたけど、\*\*セットし忘れて空っぽ（null）\*\*だった！

---

### 💻 Javaコードで書くと…

```java
public class UseItem {
    public static void main(String[] args) {
        String item = null; // どうぐが何もセットされていない

        try {
            // nullなのに使おうとしてしまう
            System.out.println("使ったどうぐは：" + item.toUpperCase());
        } catch (NullPointerException e) {
            System.out.println("どうぐがセットされていません！");
            System.out.println("→ ピカチュウは自分の力で戦った！");
        }
    }
}
```

---

### 🖨 出力結果

```
どうぐがセットされていません！
→ ピカチュウは自分の力で戦った！
```

---

## 🏠 実生活のたとえ：空のコップで水を飲もうとした

水を入れていないコップでゴクッ… → 何もない！

---

## ✅ ここまでの例３－４のまとめ表

| エラー名                             | 意味           | ポケモンの例            | 出力例           |
| -------------------------------- | ------------ | ----------------- | ------------- |
| `Exception`                      | 一般的なエラー      | PP不足で技が出せない       | 「代わりの技を使った！」  |
| `ArrayIndexOutOfBoundsException` | 配列の外を見た      | いないポケモンを呼び出す      | 「そんなポケモンいない！」 |
| `NullPointerException`           | 中身がないものにアクセス | どうぐがnullなのに使おうとする | 「どうぐがありません！」  |


ありがとうございます！
それでは続編として、\*\*「ユーザー定義の例外」**と**「複数の`catch`文の使い分け」\*\*を、これまでと同様に **ポケモンと実生活の具体例**でわかりやすく解説していきます！

---

# 🔧 ユーザー定義の例外とは？

Javaには標準の例外クラス（NullPointerExceptionなど）がありますが、**自分で作った例外クラス**を使うことで、**よりわかりやすく・意図を伝えるエラー処理**ができます。

---

## 🌟 例５：ユーザー定義の例外「スタミナ不足Exception」

### 🎮 ポケモンの状況

カビゴンに「のしかかり」をさせようとしたが、スタミナが足りなかった！ → 特別な理由なので、自分でエラーを作る！

---

### 💻 Javaコードで書くと…

```java
// 自分で作った例外クラス
class StaminaTooLowException extends Exception {
    public StaminaTooLowException(String message) {
        super(message);
    }
}

public class KabigonBattle {
    public static void main(String[] args) {
        int stamina = 10;

        try {
            if (stamina < 50) {
                // 条件に合えば、自分で作った例外を投げる
                throw new StaminaTooLowException("カビゴンのスタミナが足りません！");
            }
            System.out.println("カビゴンののしかかり！");
        } catch (StaminaTooLowException e) {
            System.out.println(e.getMessage());
            System.out.println("→ カビゴンは休憩した！");
        }
    }
}
```

---

### 🖨 出力結果

```
カビゴンのスタミナが足りません！
→ カビゴンは休憩した！
```

---

## 🏠 実生活のたとえ：寝不足で運動会に出られない

運動会当日の朝、3時間しか寝てなかった → 「寝不足Exception」を投げて体育を休む！

---

## 🧠 なぜ使うの？

* 通常の`Exception`では伝わりにくい「特別な理由」を明示できる
* チーム開発などで意図が伝わりやすくなる

---

# 🎭 複数のcatch文の使い分け

### いろんなトラブルが起こる可能性があるとき、それぞれに**別々の対応**をしたいときに使います！

---

## 🌪️ 例６：ポケモン道具と配列とnullチェックの複合例

### 🎮 ポケモンの状況

* アイテムが**null**の可能性がある
* アイテム一覧から**存在しない場所を読んでしまう可能性**がある
* どちらも起こるかもしれない！

---

### 💻 Javaコードで書くと…

```java
public class MultiCatch {
    public static void main(String[] args) {
        String[] items = new String[3];
        items[0] = null; // どうぐがセットされていない

        try {
            // まず存在しないインデックスを見る → ArrayIndexOutOfBoundsException
            String item = items[5].toLowerCase();

            // もしnullが入っていたら → NullPointerException
            System.out.println("使うアイテムは：" + item);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("そんな番号のアイテムはありません！");
        } catch (NullPointerException e) {
            System.out.println("アイテムがセットされていません！");
        } catch (Exception e) {
            System.out.println("その他のエラーが発生しました：" + e.getMessage());
        }
    }
}
```

---

### 🖨 出力結果

```
そんな番号のアイテムはありません！
```

---

## ✅ 例5－6のポイント整理

| 特徴                   | 内容                 | 使用例                 |
| -------------------- | ------------------ | ------------------- |
| `catch` を複数使う        | 異なるトラブルに異なる対応      | null、配列のはみ出しなど      |
| `ユーザー定義例外`           | 独自の名前と意味をもったエラー    | スタミナ不足、マナー違反など      |
| `Exception` の親子関係に注意 | 親クラスの catch は最後に書く | `Exception` は一番下に置く |

---

## 🎓 例１－６のまとめ

Javaの例外処理にはいろんなレベルがあります。

* ✅ `try` + `catch` 基本の仕組み
* ✅ `ArrayIndexOutOfBoundsException` や `NullPointerException` の対処
* ✅ `throw` で自分から例外を投げる
* ✅ `ユーザー定義例外` を使ってオリジナルのエラーをつくる
* ✅ `catch` を複数使ってエラーごとに別対応！

これらをうまく使うことで、**予測不能な状況にも強い、やさしいプログラム**が作れるようになります！

---

了解しました！
以下に、先ほどの例を「**例7**」からの連番として整理し直し、表記と構成もこれまでの形式に統一してお届けします。

---

## 🔚 例７：`finally` 文 〜バトル後の回復タイム〜

### 🎮 ポケモンの状況

バトルに成功しても失敗しても、**バトル後には必ずポケセンで回復！**

---

### 💻 Javaコードで書くと…

```java
public class PokemonBattle {
    public static void main(String[] args) {
        try {
            System.out.println("ピカチュウ、でんこうせっか！");
            // 技が外れたとして例外発生
            throw new Exception("攻撃がはずれた！");
        } catch (Exception e) {
            System.out.println("エラー発生：" + e.getMessage());
        } finally {
            // ここは「必ず」実行される
            System.out.println("→ ピカチュウはポケモンセンターで回復しました！");
        }
    }
}
```

---

### 🖨 出力結果

```
ピカチュウ、でんこうせっか！
エラー発生：攻撃がはずれた！
→ ピカチュウはポケモンセンターで回復しました！
```

---

## 🏠 実生活のたとえ

お料理で焦がしても、うまく焼けても、**必ず洗い物をする！**

---

## ✅ 解説ポイント

* `finally` ブロックは、**例外が起きても・起きなくても必ず実行される**
* 主に「**後片付け処理**」や「**ログ出力**」などに使用

---

## 📁 例８：`try-with-resources` 〜ファイルを自動で閉じる〜

### 🎮 ポケモンの状況

サトシがバトルの記録をノートに書いたあと、**閉じ忘れて雨でぐちゃぐちゃに！**

---

### 💻 Javaコードで書くと…

```java
import java.io.*;

public class Diary {
    public static void main(String[] args) {
        // tryの()内でファイルを書き込み用に開く
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("pokemon_diary.txt"))) {
            writer.write("ピカチュウがライチュウに進化した！");
            System.out.println("→ バトル日記を保存しました。");
        } catch (IOException e) {
            System.out.println("ファイル保存中にエラー：" + e.getMessage());
        }
    }
}
```

---

### 🖨 出力結果

```
→ バトル日記を保存しました。
```

📁 ※ ファイルは自動的に閉じられ、閉じ忘れによるトラブルを防ぎます。

---

## 🏠 実生活のたとえ

**自動でノートを閉じてくれる文房具**みたいなイメージです。

---

## ✅ 解説ポイント

* `try(...)` の括弧内に書かれた**リソースは自動で閉じられる**
* **ファイルやネット接続**などの後始末がラクに、安全になる！

---

## 🪤 例９：その他の応用テクニック

---

### ① 複数catchを1つにまとめる（Java 7以降）

```java
try {
    // 処理中にいろんな問題が起きるかも…
} catch (IOException | NullPointerException e) {
    System.out.println("IOエラーまたはnullです：" + e.getMessage());
}
```

📌 似たような対処をしたい場合は**1つのcatchに統合**できます！

---

### ② 例外の再スロー（throw again）

```java
try {
    throw new IOException("ファイルが読めません");
} catch (IOException e) {
    System.out.println("ログ記録：" + e.getMessage());
    throw e; // 外にもう一度投げる
}
```

📌 エラーの**報告だけして、処理は上の人（上のコード）に任せる**。

---

### ③ `throw` と `throws` の違い

| 用語       | 説明                   | 使用例                                          |
| -------- | -------------------- | -------------------------------------------- |
| `throw`  | 実際に例外を「投げる」          | `throw new Exception("エラー")`                 |
| `throws` | メソッドが例外を「投げるかも」と宣言する | `public void doSomething() throws Exception` |

---

## ✅ 例７－９まとめ

| 例  | 内容                         | ポケモンのたとえ     |
| -- | -------------------------- | ------------ |
| 例７ | `finally`：絶対に実行            | バトル後の回復      |
| 例８ | `try-with-resources`：自動後始末 | ノートを自動で閉じる   |
| 例９ | 複数catchや再スローなど             | 対応を一括化・責任を渡す |

---

承知しました！
最後に「**チェック例外 vs 非チェック例外の違い**」と「**実務でのベストプラクティス**」について、例10から始めて丁寧に解説します。
これまでと同様に、**ポケモンの例**や**実生活の例**を交え、中学生にも理解できるように構成しています。

---

## ⚖️ 例１０：チェック例外 vs 非チェック例外（Runtime例外）の違い

---

### 📚 用語のおさらい

| 種類                            | 説明                               | 特徴                               |
| ----------------------------- | -------------------------------- | -------------------------------- |
| **チェック例外**                    | Javaで「**この例外は必ず対処しなさい**」と指示されるもの | コンパイル時に**catch**または**throws**が必要 |
| **非チェック例外（RuntimeException）** | Javaで「**対処してもしなくてもいいよ**」とされるもの   | 予測困難・コードミス系が多い                   |

---

### 🎮 ポケモンでたとえると…

#### ◯ チェック例外

📦 サトシが荷物を送るとき、「**壊れ物です！扱いに注意してね**」と必ず伝える必要がある。
（→ Javaでも開発者が**対処を強制される**）

#### ◯ 非チェック例外（Runtime）

🌀 サトシが急に道に迷う！地図を持ってなかった！
（→ Javaでも突然のNullPointerExceptionなどが**勝手に発生する**）

---

### 💻 チェック例外のコード例

```java
import java.io.*;

public class CheckedExample {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("data.txt")); // ファイルがないかも
        } catch (IOException e) {
            System.out.println("ファイルが見つかりません！");
        }
    }
}
```

☑ **ファイル読み込みなど、現実世界のエラーに多い**

---

### 💻 非チェック例外のコード例

```java
public class UncheckedExample {
    public static void main(String[] args) {
        String name = null;
        System.out.println(name.toUpperCase()); // ← null で例外が出る
    }
}
```

☑ **プログラマーのミスやバグに由来することが多い**

---

### 🧠 実生活のたとえ

| 種類      | 実生活での例            | たとえ            |
| ------- | ----------------- | -------------- |
| チェック例外  | 郵便を送るとき「割れ物注意」が必須 | 明らかに気をつけるべきこと  |
| 非チェック例外 | スマホを急に落とす         | 予測が難しくて突然起きること |

---

## 💼 例１１：実務でのベストプラクティス

---

### ✅ 基本方針

| 原則                                            | 内容                       |
| --------------------------------------------- | ------------------------ |
| ❶ 例外は**使いすぎない**                               | 例外は特別な事態用。通常のフローには使わない   |
| ❷ **チェック例外は明示的に処理する**                         | ユーザーのミスや外部環境の影響に備える      |
| ❸ **RuntimeExceptionは防げるようコードで対策**            | Nullチェック、バリデーションの徹底      |
| ❹ エラー内容は**具体的なメッセージで出す**                      | 何が悪かったのか、次に何をすればいいか明示    |
| ❺ `finally`や`try-with-resources`で**後始末**を忘れない | ファイル、ネット接続、データベースなど必ず閉じる |

---

### 🎯 実務でありがちなNGとOK

| 状況        | NG例                   | OK例                      |
| --------- | --------------------- | ------------------------ |
| Nullチェック  | いきなり `.toUpperCase()` | `if (name != null)`      |
| ファイル操作    | 開いて閉じ忘れる              | `try-with-resources` を使う |
| catchブロック | 何も書かずに握りつぶす           | ログに記録して次の処理をする           |
| エラーメッセージ  | 「エラーが起きました」           | 「入力ファイルが存在しません」          |

---

### 🎮 ポケモン実務編（イメージ）

* サトシが「モンスターボールが壊れてるかも」と思ったら、**事前にチェックするのが正解**
* それでも壊れてたら、**ちゃんとエラーとして伝えて対処**

---

## 🧠 例１０－１１のまとめ

| 例   | 内容                | ポケモンたとえ         |
| --- | ----------------- | --------------- |
| 例１０ | チェック例外 vs 非チェック例外 | 荷物と落とし物の違い      |
| 例１１ | 実務での使い方の工夫        | エラーを防ぐ・伝える・片付ける |

---

これで、Javaの**例外処理の入門から実践レベルまで**を網羅しました！

---

## 📘 Javaの代表的な例外クラス 一覧（10選）

| 🧪 例外クラス名                       | 🔍 説明（どんなときに出る？）                                  | 💡 よくある例                                          |
|----------------------------------|------------------------------------------------------------|-----------------------------------------------------|
| `NullPointerException`          | 「null」の変数を使おうとしたとき                           | ピカチュウの技をセットしてないのに使おうとした       |
| `ArrayIndexOutOfBoundsException`| 配列の範囲外にアクセスしようとした                         | ポケモンリストの3番目を取り出そうとした（2つしかない）|
| `ArithmeticException`           | 数学の計算でエラー（0で割るなど）                          | HP / 0 のような割り算                                |
| `NumberFormatException`         | 文字列を数値に変換できなかった                            | `Integer.parseInt("abc")`                           |
| `ClassCastException`            | 型変換ができなかった                                     | ポケモン → トレーナーにキャストしようとした         |
| `IOException`                   | 入出力エラー（ファイルや通信）                            | ファイルを開こうとして失敗                           |
| `FileNotFoundException`         | ファイルが見つからなかった（IOExceptionの子）             | `new FileReader("data.txt")`                        |
| `IllegalArgumentException`      | 渡した引数が不正だった                                   | レベルに -1 を渡した                                 |
| `IndexOutOfBoundsException`     | Listなどで範囲外にアクセスした                            | `list.get(10)` のように存在しない番号               |
| `Exception`                     | すべての例外の親クラス。catchで全部まとめて受け取れる     | なんでもキャッチしたいとき                           |

---

## 📎 例外処理クラス注意点

- `Exception` はすべての例外の親クラス。
- `RuntimeException` 系は**実行時**に発生する。
- `IOException` 系は**事前に注意して書く必要がある（チェック例外）**。

---


# 🧪 ポケモンで学ぶ！Javaの例外クラス10選

Javaでは「例外処理（Exception）」を使って、プログラム中の問題を安全に処理できます。  
ここでは **ポケモンを題材** にして、Javaの代表的な例外クラスを10つ紹介します。

---

## 1. `NullPointerException`：nullのオブジェクトを使うときのエラー

### 🌟 サンプルコード

```java
// ポケモンの技が設定されていない（null）状態で使おうとする例
public class NullPointerExample {
    public static void main(String[] args) {
        String move = null; // 技がセットされていない
        System.out.println("使うわざ：" + move.length()); // nullのlengthを呼び出すと例外
    }
}
````

### 🧾 出力例

```
Exception in thread "main" java.lang.NullPointerException
```

### 💡 解説

* `move` はnullのままで `.length()` を呼び出そうとしてしまい、`NullPointerException` が発生しています。

---

## 2. `ArrayIndexOutOfBoundsException`：配列の外をアクセスしたときのエラー

### 🌟 サンプルコード

```java
// ポケモンのリストから存在しない番号のポケモンを選ぶ例
public class ArrayIndexExample {
    public static void main(String[] args) {
        String[] pokemons = {"ピカチュウ", "ヒトカゲ"};
        System.out.println("選んだポケモン：" + pokemons[3]); // 2つしかないのに3番目を選ぼうとしている
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 2
```

### 💡 解説

* 配列 `pokemons` に存在しないインデックス `[3]` を指定したため、範囲外アクセスで例外が発生します。

---

## 3. `ArithmeticException`：0で割り算したときのエラー

### 🌟 サンプルコード

```java
// ポケモンのHPを0で割って回復率を求める例
public class ArithmeticExample {
    public static void main(String[] args) {
        int hp = 0;
        int rate = 100 / hp; // 0で割ろうとしている
        System.out.println("回復率：" + rate);
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.ArithmeticException: / by zero
```

### 💡 解説

* 0で割り算しようとしたため `ArithmeticException` が発生しました。

---

## 4. `NumberFormatException`：数字じゃない文字列を数値に変換しようとしたときのエラー

### 🌟 サンプルコード

```java
// ポケモンのレベルを文字列から数値に変換する例
public class NumberFormatExample {
    public static void main(String[] args) {
        String levelStr = "abc"; // 数字じゃない
        int level = Integer.parseInt(levelStr); // 数値に変換できない
        System.out.println("レベル：" + level);
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.NumberFormatException: For input string: "abc"
```

### 💡 解説

* "abc" は数字でないため、数値変換できずに `NumberFormatException` が発生します。

---

## 5. `ClassCastException`：間違った型変換をしようとしたときのエラー

### 🌟 サンプルコード

```java
// Objectとして扱っていたポケモンを、間違ってトレーナーとして変換しようとする例
public class ClassCastExample {
    public static void main(String[] args) {
        Object obj = "ピカチュウ";
        Integer trainer = (Integer) obj; // 文字列をIntegerにキャストしようとしている
        System.out.println(trainer);
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.ClassCastException
```

### 💡 解説

* `String` 型のオブジェクトを `Integer` に変換しようとして失敗し、`ClassCastException` が発生します。

---

## 6. `IOException`：ファイルの入出力で問題が起きたときのエラー

### 🌟 サンプルコード

```java
// ファイルを読もうとして入出力エラーが起きる例
import java.io.*;

public class IOExceptionExample {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader("pokemon.txt")); // ファイルが存在しない場合
        System.out.println(reader.readLine());
        reader.close();
    }
}
````

### 🧾 出力例

```
Exception in thread "main" java.io.FileNotFoundException: pokemon.txt (No such file or directory)
```

### 💡 解説

* `FileReader` でファイルが見つからなかったため、`IOException` の子クラス `FileNotFoundException` が発生しています。

---

## 7. `FileNotFoundException`：指定したファイルが見つからなかったときのエラー

### 🌟 サンプルコード

```java
// ファイルが見つからない例
import java.io.*;
import java.util.Scanner;

public class FileNotFoundExample {
    public static void main(String[] args) throws FileNotFoundException {
        File file = new File("missing_pokemon.txt");
        Scanner scanner = new Scanner(file); // 存在しないファイルを開こうとする
        System.out.println(scanner.nextLine());
        scanner.close();
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.io.FileNotFoundException: missing_pokemon.txt (No such file or directory)
```

### 💡 解説

* 存在しないファイル `"missing_pokemon.txt"` を読み込もうとしたため、`FileNotFoundException` が発生します。

---

## 8. `IllegalArgumentException`：メソッドに不正な値を渡したときのエラー

### 🌟 サンプルコード

```java
// ポケモンのレベルにマイナスを入れてエラーにする例
public class IllegalArgumentExample {
    public static void main(String[] args) {
        setPokemonLevel(-5); // 不正な引数
    }

    public static void setPokemonLevel(int level) {
        if (level < 0) {
            throw new IllegalArgumentException("レベルは0以上である必要があります。");
        }
        System.out.println("ポケモンのレベル：" + level);
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.IllegalArgumentException: レベルは0以上である必要があります。
```

### 💡 解説

* メソッドに「レベル -5」という不正な値を渡したため、`IllegalArgumentException` を開発者側で `throw` しています。

---

## 9. `IndexOutOfBoundsException`：Listなどで範囲外アクセスしたときのエラー

### 🌟 サンプルコード

```java
// ArrayListで存在しないインデックスを呼び出す例
import java.util.*;

public class IndexOutOfBoundsExample {
    public static void main(String[] args) {
        List<String> pokemonList = new ArrayList<>();
        pokemonList.add("ピカチュウ");
        System.out.println(pokemonList.get(5)); // 存在しないインデックス
    }
}
```

### 🧾 出力例

```
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index 5 out of bounds for length 1
```

### 💡 解説

* `pokemonList.get(5)` は、存在しないインデックスを参照しているため例外が発生します。

---

## 10. `Exception`：すべての例外の親クラス

### 🌟 サンプルコード

```java
// try-catchで全例外をまとめてキャッチする例
public class GeneralExceptionExample {
    public static void main(String[] args) {
        try {
            throw new Exception("ポケモン例外発生！");
        } catch (Exception e) {
            System.out.println("キャッチしました：" + e.getMessage());
        }
    }
}
```

### 🧾 出力例

```
キャッチしました：ポケモン例外発生！
```

### 💡 解説

* `Exception` をcatchすれば、あらゆる種類の例外をまとめて処理することができます。

---

## 💡 例外クラス10選

| 例外クラス名                           | 用途・発生条件         | 代表的な例                                            |
| -------------------------------- | --------------- | ------------------------------------------------ |
| `NullPointerException`           | nullを使おうとした     | `obj.length()` を obj が null のまま呼ぶ                |
| `ArrayIndexOutOfBoundsException` | 配列の外を参照した       | 配列にないインデックス `pokemons[3]` を参照                    |
| `ArithmeticException`            | 0で割るなど、計算時のミス   | `100 / 0`                                        |
| `NumberFormatException`          | 数字に変換できない文字列    | `Integer.parseInt("abc")`                        |
| `ClassCastException`             | 不正な型変換を行った      | `Object obj = "abc"; Integer x = (Integer) obj;` |
| `IOException`                    | 入出力処理での一般的なエラー  | ファイル読み込み時に I/O 失敗                                |
| `FileNotFoundException`          | ファイルが見つからない     | `new FileReader("no_file.txt")`                  |
| `IllegalArgumentException`       | 不正な引数をメソッドに渡した  | マイナスのレベルをセット `setLevel(-1)`                      |
| `IndexOutOfBoundsException`      | Listや配列で範囲外アクセス | `list.get(100)`                                  |
| `Exception`                      | すべての例外の親クラス     | 例外をひとまとめに処理するときに使用                               |

---

## 📚 総まとめ

* `IOException` や `FileNotFoundException` はファイル操作に必須
* `IllegalArgumentException` は「ルール違反」をプログラムでチェックするときに便利
* `Exception` は親クラスとして、最後の砦的にcatchできます

---

