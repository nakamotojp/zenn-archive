---
title: Javaの基本概念をモンスター育成ゲームで理解する
tags: Java プログラミング初心者 ポケモン
author: nakamoto
slide: false
---
画像は `ChatGPT4o` で生成したものです。
# Javaの初学者の方向けに、Javaを好きになりながら基本概念をイメージしてもらう目的で書いています。
1. ゲームを起動する
1. 変数というボール
1. 配列というボールケース
1. データの種類（データ型）
1. もし〇〇だったらというif文
1. ◯回繰り返すfor文
1. 表示させる
1. 入力する
1. メソッドというモンスターのわざ
1. 
## ゲームを起動する
`コード内の日本語表記はプログラマーが変更するところだと思ってください`
``` java
// アプリを起動した瞬間
package モンスター育成パッケージ;
import java.util;
public class App {
  // ゲーム画面が表示される瞬間
  public static void main(String[] args) {
    String ボール = "黄色いピカピカしたモンスター";
    }
  }
}
```
## オブジェクト
プログラミングを学習する時、私がずっと腑に落ちなかった概念にオブジェクトというものがあります。
学習時、オブジェクトというのは物であると教わりました。
英語でいうとものです。
いまだからわかります、物です。
でも、イメージが付きませんよね。
「ここにゲーム画面の画像をいれる」
ゲームをしていると、それより先に進めない木や岩があると思います。
それが、オブジェクトです。
私の中で、最もイメージが付いたのが、ゲーム内の木や岩でした。
通れないからオブジェクトということでは有りません。
フォートナイトのように壊せる木や岩もオブジェクトです。
壊せるかどうかが重要ではなく、手に持っているボールもオブジェクトです。
プレイヤーのキャラクターも敵キャラクターもオブジェクトです。
つまり、ゲーム世界に存在するもすべてがオブジェクトです。
オブジェクトは、存在するものひとつひとつ、すべてのことを意味します
もちろん、モンスターもオブジェクトです。
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/67fbc166-3f68-4ff5-896d-f2ae86c917f8.png)
## 変数
変数はモンスターを入れておくボールだと思ってください。
モンスター育成ゲームでは、モンスターと一緒に旅をします。
モンスターは１００や２００に増えるため、すべてのモンスターと二人三脚で歩くのも大変です。
そこで、モンスターを変数というボールに入れておきます。
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/38650187-01f0-4c49-94a7-231f845660ec.png)
次のコードは、 `ボール` 変数に `黄色いピカピカしたモンスター` を入れた状態です。
`ボール` という変数名は自由に変更可能です。
``` java
// アプリを起動した瞬間
package モンスター育成パッケージ;
import java.util;
public class App {
  // ゲーム画面が表示される瞬間
  public static void main(String[] args) {
    String ボール = "黄色いピカピカしたモンスター";
    }
  }
}
```
これにより、次の `黄色いピカピカしたモンスター` の歩幅に合わせて歩く必要がなくなり、 `黄色いピカピカしたモンスター` が疲れたから抱っこし続ける必要もなく、 `ボール` を持ち運べば良く、旅の足取りが軽くなります。
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/cf72cfb9-b5f6-4eef-836d-ca5b2b5295cb.png)
### 配列
配列とは、ボールを管理する箱です。
`黄色いピカピカしたモンスター` を `ボール` に入れて旅をする方法もありますが、 `ボール` という変数が10個ぐらいになってくると、どのボールに何が入っているか管理するのが大変になります。
そこで、 `ボール変数` をまとめて管理する専用のケースである `配列` を使います。
今回は `ボールを8個まとめる専用ケースの配列` をイメージして考えましょう。
黄色の2つのボール変数には、どちらも `黄色いピカピカしたモンスター` が入っています。
他の色のボールには、それぞれ、`水色のそーなんだーって感じるモンスター` や `赤色のファイヤーボール出しそうなモンスター` が入っていたりします。
配列という専用のケースに入れているだけで、一気にすべてのモンスターを回復させることができます。
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/6c5f7a78-e097-409c-9b05-91e44f07a60e.png)
また、 `0` 番目に入っているモンスターだけを個別に指定して取り出すことも可能です。
![回復カプセル配列.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/3a80142c-3900-42e9-9f93-635f35a30bab.png)
### インデックス
`0` 番目に入っているモンスターだけを個別に指定して扱うことを配列といいます。
注意点として、1番最初の値が0番目から始まるという考え方です。
つまり、ボールが8個あったら、 `0番目から7番目までの配列` と言う呼び方で指定します。
この番号をインデックスと呼びます。
日本語では添字と呼ばれますが、最初は理解しやすい用語を使うと良いので `番号` でよいです。
## クラス
### クラス利用前の事情
あなたはモンスター育成ゲームの管理者です。
管理者はゲームの世界をただ見ているだけでなく、プレイヤーの動きに応じて、モンスターを適切に配置する必要があります。
そうしないと、最初の町から出た時に伝説のモンスターとであったり、そもそもモンスターが出なかったりするからです。
モンスターを配置するに当たり、 `ピカモン` というモンスターを作ります。
`ピカモン` は皆がよく知っているモンスターなので、積極的に配置したいです。
しかし、 `ピカモン` を配置するのに、1ピカモンあたり、100行程度のコードを実装する必要があります。
100行書けばよいのですが、ミスすることもありますし、仕様が変わることもあります。
毎回100行書いたコードで、世界に1000体の `ピカモン` を配置したあと、 `ピカモン` の攻撃力を一律で上げようとすると、1000箇所のコードを書き換える必要があります。
この課題を解決するのがクラスです。
### クラスは設計図
クラスはピカモンを作るための設計図です。
ピカモンの設計図というクラスには100行のコードが実装されています。
つまり、ピカモンの設計図を実行することで、だれでもきれいな100行のコードを利用でき、確実にピカモンを作り出すことができます。
### フィールド
オブジェクトがもっているデータです。
モンスター育成ゲームであれば、モンスターが持っているデータです。
クラスを利用せず、都度モンスターを配置するということは、次のふぃーるどを都度実装する必要があるということになります。
``` java
    private int number = 0; // モンスター番号
    private String name = null; // モンスター名称
    private String category = null; // モンスター分類
    private String type1 = null; // モンスタータイプ1
    private String type2 = null; // モンスタータイプ2
    private double height = 0; // モンスターの身長
    private double weight = 0; // モンスターの体重
    private String description = null; // モンスター説明
    private String sing = null; // モンスターの鳴き声
    private int vitality = 0; // モンスターの体力
    private int agility = 0; // モンスターの素早さ
    private int attach = 0; // モンスターの攻撃力
    private int defence = 0; // モンスターの防御力
    private int exp = 0; // モンスターの経験値
    private int specialAttack = 0; // モンスターの特攻
    private int specialDevence = 0; // モンスターの特防
```
命名規則：https://qiita.com/rkonno/items/1b30daf83854fecbb814
### メソッド
「 攻撃する 」、「 鳴く 」、「 逃げる 」のような、オブジェクトの行動を処理として実装したものです。
モンスター育成ゲームであれば、モンスターが使う技です。
クラスを利用せず、都度モンスターを配置するということは、次のメソッドを都度実装する必要があるということになります。
``` java
    // --- staticメソッド（クラスメソッド） ---
    public static int getMonsterCount() {
        return monsterCount;
    }
    public static void showMonsterInfoFormat() {
        System.out.println("【モンスター情報フォーマット】");
        System.out.println("名前 / 分類 / タイプ1, タイプ2 / ステータス...");
    }
    // --- インスタンスメソッド ---
    public void cry() {
        System.out.println(name + " は鳴いた: \"" + sing + "\"");
    }
    public void showStatus() {
        System.out.println("==== " + name + " のステータス ====");
        System.out.println("分類: " + category + " / タイプ: " + type1 + (type2 != null ? ", " + type2 : ""));
        System.out.println("体力: " + vitality + " 攻撃: " + attack + " 防御: " + defence);
        System.out.println("特攻: " + specialAttack + " 特防: " + specialDefence + " 素早さ: " + agility);
        System.out.println("経験値: " + exp);
    }
    public void levelUp() {
        if (exp >= 100) {
            System.out.println(name + " はレベルアップした！");
            vitality += 5;
            attack += 3;
            defence += 3;
            specialAttack += 2;
            specialDefence += 2;
            agility += 2;
            exp = 0;
        } else {
            System.out.println(name + " はまだレベルアップできない。");
        }
    }
    public void gainExp(int gainedExp) {
        System.out.println(name + " は " + gainedExp + " の経験値を得た！");
        this.exp += gainedExp;
    }
```
### クラス利用後の世界
ピカモンという設計図さえしっかりしていれば、本日加入されたエンジニアであっても、適切にピカモンを配置することが可能です。
それだけでなく、クラスを利用した配置したピカモンの攻撃力だけ上げたいなって時には、ピカモンクラスの攻撃力だけ上げておけば、その後のピカモンはあがった攻撃力のピカ門になります。
もちろん、以前のクラスで配置したピカモンの攻撃力だけ上げることも可能です。
### クラス宣言
``` java
public class Monster {
    // --- フィールド（インスタンス変数） ---
    // クラスの各インスタンスに固有のデータを保持する変数

    private int number = 0;
    private String name = null;
    private String category = null;
    private String type1 = null;
    private String type2 = null;
    private double height = 0;
    private double weight = 0;
    private String description = null;
    private String sing = null;
    private int vitality = 0;
    private int agility = 0;
    private int attack = 0;
    private int defence = 0;
    private int exp = 0;
    private int specialAttack = 0;
    private int specialDefence = 0;
    // --- クラス変数（static変数） ---
    // この変数は全インスタンスで共有される（個々のオブジェクトではなく、クラス全体で管理）
    private static int monsterCount = 0; // 生成されたモンスターの数を記録
    // --- コンストラクタ ---
    // クラスのインスタンスが生成されるときに実行される

    public Monster(String name) {
        this.name = name; // 名前を設定
        monsterCount++;   // 生成されたモンスターの総数を更新
    }
    // --- staticメソッド（クラスメソッド） ---
    // staticメソッドはインスタンスを生成しなくても呼び出せる
    public static int getMonsterCount() {
        return monsterCount; // 現在のモンスター数を返す

    }
    public static void showMonsterInfoFormat() {
        System.out.println("【モンスター情報フォーマット】");
        System.out.println("名前 / 分類 / タイプ1, タイプ2 / ステータス...");
    }
    // --- インスタンスメソッド ---
    // インスタンスごとに実行されるメソッド（個別のオブジェクトに依存）

    public void cry() {
        System.out.println(name + " は鳴いた: \"" + sing + "\"");
    }
    public void showStatus() {
        System.out.println("==== " + name + " のステータス ====");
        System.out.println("分類: " + category + " / タイプ: " + type1 + (type2 != null ? ", " + type2 : ""));
        System.out.println("体力: " + vitality + " 攻撃: " + attack + " 防御: " + defence);
        System.out.println("特攻: " + specialAttack + " 特防: " + specialDefence + " 素早さ: " + agility);
        System.out.println("経験値: " + exp);
    }
    public void levelUp() {
        if (exp >= 100) { // 経験値が 100 以上ならレベルアップ

            System.out.println(name + " はレベルアップした！");
            vitality += 5;
            attack += 3;
            defence += 3;
            specialAttack += 2;
            specialDefence += 2;
            agility += 2;
            exp = 0; // レベルアップ後、経験値をリセット

        } else {
            System.out.println(name + " はまだレベルアップできない。");
        }
    }
    public void gainExp(int gainedExp) {
        System.out.println(name + " は " + gainedExp + " の経験値を得た！");
        this.exp += gainedExp; // 経験値を加算

    }
    // --- プロパティ（getter/setter） ---
    // フィールドへの安全なアクセスを提供するメソッド

    public String getName() { return name; } // name フィールドの値を取得
    public void setSing(String sing) { this.sing = sing; } // sing フィールドの値を設定
    public void setExp(int exp) { this.exp = exp; } // exp フィールドの値を設定
}
```
### クラス実行
``` java
public class Main {
    public static void main(String[] args) {
        // staticメソッドの呼び出し（インスタンス不要）
        // staticメソッドは Monster.getMonsterCount() のように呼び出す
        Monster.showMonsterInfoFormat();
        System.out.println("モンスター数（初期）: " + Monster.getMonsterCount());
        // モンスター生成（インスタンスメソッドを使用するために）
        // インスタンスメソッドは new Monster() 後に m1.cry() のように使う
        Monster m1 = new Monster("ドラコ");
        m1.setSing("グワァァァ！");
        m1.setExp(120);
        // インスタンスメソッドの呼び出し
        m1.cry();          // 鳴く
        m1.showStatus();   // ステータス表示
        m1.levelUp();      // レベルアップ確認
        // staticで数の確認
        System.out.println("モンスター数（生成後）: " + Monster.getMonsterCount());
    }
}
```
### クラス実行結果簡略例
``` java
【モンスター情報フォーマット】
名前 / 分類 / タイプ1, タイプ2 / ステータス...
モンスター数（初期）: 0
ドラコ は鳴いた: "グワァァァ！"
==== ドラコ のステータス ====
分類: null / タイプ: null
体力: 0 攻撃: 0 防御: 0
特攻: 0 特防: 0 素早さ: 0
経験値: 120
ドラコ はレベルアップした！
モンスター数（生成後）: 1
```
## 継承
クラスのお陰でピカモンを簡単に配置することができました。
育成ゲーム管理者としての仕事もだいぶ楽になりました。
楽になったのでピカモンと似たような、ライモンというモンスターを作ることになりました。
ゲーム管理者「この前ピカモンを100行コード書いて作ったのに・・・またゼロから考えるのか・・・」
そう思いますよね。
でも、ご安心ください。
Javaの継承を利用して簡単にライモンを配置できます。
継承というのは、ライモンとにているピカモンのコードを受け継いで、ライモンを作ることです。
ピカモンには無い性質を、ライモンクラスに追記することで、ゲームとしての拡張性を高めることが可能です。
## `extends`
``` java
class ピカモン {
    100行のコードの一部
    public String 万ボルト() {
        100行のコードの一部
	    return "効果バツグンだったりそうでなかったり";
    }
}
class ライモン extends ピカモン {
    100行のコードの一部
    public String 電気玉半減() {
        100行のコードの一部
	    return "電気玉保有時に攻撃と特功がピカモンの半分";
    }
}
```
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/4f279a79-672c-4c94-b730-1fb6167aa2f7.png)
## リファクタリング
さて、ピカモンを継承して、ライモンを配置しました。
ただ、よく考えたら、ピカモンを元に継承するより、モンスター共通のクラスを作って、継承した方が良い事に気づきました。
何故なら、モンスターは、⚡️雷モンスターのピカモンだけでは無く、💦水を使うモンスターや、🔥火を使うモンスターもいるからです。
いろいろなモンスターの親とも言える、スーパー凄い元になる設計図となるモンスタークラスを、親クラスやスーパークラスと言います。
親クラスやスーパークラスを元に作成されるモンスターのクラスを、子クラスやサブクラスと言います。
親↔︎子
スーパー↔︎サブ
意味は同じです。
それでは、モンスタークラスを利用して継承する例を書いてみましょう。
## モンスターゲームでの実装例
``` java
public class Pikamon extends Monster {
    // コンストラクタ
    public Pikamon() {
        super("ピカモン"); // 名前は固定で渡す
        this.setSing("ピカァァ！");
        this.setCategory("でんきネズミ");
        this.setType1("でんき");
        this.setHeight(0.4);
        this.setWeight(6.0);
        this.setExp(50);
        // ステータスの初期値を設定
        this.setVitality(35);
        this.setAttack(55);
        this.setDefence(30);
        this.setSpecialAttack(50);
        this.setSpecialDefence(40);
        this.setAgility(90);
    }
    // ピカモン固有の動作
    public void thunderShock() {
        System.out.println(this.getName() + " は でんきショック を放った！");
    }
    // オーバーライド：鳴き方を特別に
    @Override
    public void cry() {
        System.out.println("⚡️ " + this.getName() + " の鳴き声: \"" + this.getSing() + "\" ⚡️");
    }
}
```
### モンスターゲームでの実行例
``` java
public class Main {
    public static void main(String[] args) {
        // モンスターのテンプレート呼び出し
        Monster.showMonsterInfoFormat();
        // Pikamonのインスタンス生成
        Pikamon pika = new Pikamon();
        // 継承したメソッド
        pika.cry();          // オーバーライドされた鳴き方
        pika.showStatus();   // 継承したステータス表示
        pika.gainExp(60);    // 経験値追加
        pika.levelUp();      // レベルアップ処理
        // Pikamon独自のメソッド
        pika.thunderShock();
        // staticメソッドの呼び出し
        System.out.println("モンスター数: " + Monster.getMonsterCount());
    }
}
```
### モンスターゲームでの実行結果例
``` java
【モンスター情報フォーマット】
名前 / 分類 / タイプ1, タイプ2 / ステータス...
⚡️ ピカモン の鳴き声: "ピカァァ！" ⚡️
==== ピカモン のステータス ====
分類: でんきネズミ / タイプ: でんき
体力: 35 攻撃: 55 防御: 30
特攻: 50 特防: 40 素早さ: 90
経験値: 50
ピカモン は 60 の経験値を得た！
ピカモン はレベルアップした！
ピカモン は でんきショック を放った！
モンスター数: 1
```
### 💡 学習ポイントまとめ
extends:	Monsterクラスを継承してPikamonを定義
super():	親クラスのコンストラクタを呼び出して名前設定
@Override:	cry() をピカモン専用に上書き
## ポリモーフィズム
## 質問する方法
1. 「むしろ「助けて」がちゃんと言えるだけでも十分偉い」参照：https://blog.tinect.jp/?p=89263
```
-手遅れになる前に「困っています」を出力できている
-何がしたくて、何が出来ていないかを言語化できている
-何をやろうとしたか、どこまで試みたかを言語化できている
-普段の進捗をちゃんと周囲に報告・共有している
-助けを求める際、必要な人を巻き込めている
-自然と感謝の言葉を口に出来ている
```
### 困っている時に質問する例
1. 手遅れになる前に「困っています」を出力する例 
    1. 「例外処理について学んでいるんですが、エラーが出る原因が特定できず、次のステップに進めない状態です。助けていただけますか？」
    1. 「課題の提出期限が近いんですが、forループでうまく条件を設定できません。何か間違いに心当たりがありますか？」
    1. 「Javaのインストールは済んだんですが、IDEの使い方が全然わからなくて、困っています。基本操作を教えてもらえますか？」
1. 何がしたくて、何が出来ていないかを言語化する例 
    1. 「簡単なゲームを作りたくて、配列を使おうとしていますが、要素のアクセス方法がわかりません。」
    1. 「オブジェクト指向の概念を使ってコードを書きたいんですが、クラスとインスタンスの違いが理解できていない気がします。」
    1. 「データを入力して結果を表示するプログラムを作りたいのに、Scannerクラスのインポートはできていますがうまく機能しません。」
1. 何をやろうとしたか、どこまで試みたかを言語化する例 
    1. 「クラスを作成し、フィールドとメソッドを定義しましたが、メソッドが正しく呼び出せませんでした。コードを見て何が問題か教えていただけますか？」
    1. 「例外を試しに自分で投げてみたんですが、catchブロックで処理できないようです。書き方が間違っているのでしょうか？」
    1. 「リストの要素をソートするプログラムを書こうとして、Collections.sortを試しましたが、コンパイルエラーが出てしまいます。」
1. 普段の進捗を周囲と共有する例 
    1. 「今日、if文とfor文を使って簡単なプログラムを作りました！でも、コードが冗長なので改善のヒントが欲しいです。」
    1. 「配列の基本を学んで、要素を追加したり削除したりできるようになりました！次はリストを使ってみたいと考えていますが、ポイントがあれば教えてください。」
    1. 「先週やっとオブジェクト指向を使った簡単なアプリケーションを作れました！まだコードの整理方法に悩んでいます。」
1. 必要な人を巻き込む例 
    1. 「初学者同士で話し合ったんですが解決できず、経験者の方の視点が欲しいです。for文の応用について教えていただけませんか？」
    1. 「オンラインで調べてもなかなかピンとこないので、Javaに詳しい方のサポートをお願いしたいです。」
    1. 「グループディスカッションで作ったコードがエラーだらけなので、プロのアドバイスをいただけるとありがたいです！」
1. 自然と感謝の言葉を口にする例 
    1. 「おかげさまでクラスとオブジェクトの違いが理解できました！本当に助かりました！」
    1. 「教えていただいたコードの改善方法で、動作がスムーズになりました。ありがとうございます！」
    1. 「アドバイス通りに直したらエラーが解消しました！本当に感謝しています！」
## 具体的な質問文
「Java のメソッドの戻り値について質問です。現在、配列の要素数を数えるメソッド countElements を実装しようとしていますが、return 文で何を返せば良いのか分からず、困っています。
①具体的には、次のコードで、与えられた int 型の配列 array の要素数を数え、その結果を int 型で返したいと考えています。
``` Java
public int countElements(int[] array) {
    // ここに要素数を数える処理を記述
    // return ???; // 何を返せば良いか分からない
}
```
②これまでに試したこととしては、return array.length; と記述してみましたが、コンパイルエラーが発生しました。エラーメッセージは「型が一致しません」というものでした。array.length は int 型の値を返すはずなので、原因が分からず、行き詰まってしまいました。
③現況はチームのSlackチャンネルで共有しており、現在の状況も報告済みです。この問題について、〇〇さん（メンター）と△△さん（チームリーダー）にも相談しましたが、お二方とも「戻り値の型をもう一度確認してみて」というアドバイスをくださいました。しかし、何度確認しても int 型で間違いないように思えます。
お手数をおかけしますが、この問題について、何か解決策をご教授いただけないでしょうか。よろしくお願いいたします。」
ポイント:
1. 手遅れになる前に「困っています」を出力: 冒頭で「困っています」と明示的に伝えることで、質問者の状況を理解しやすくしています。
1. 何がしたくて、何が出来ていないかを言語化: 配列の要素数を数え、その結果を int 型で返したいが、return 文で何を返せば良いか分からないことを明確にしています。
1. 何をやろうとしたか、どこまで試みたかを言語化: return array.length; を試したこと、コンパイルエラーが発生したこと、エラーメッセージの内容などを具体的に記述しています。
1. 普段の進捗をちゃんと周囲に報告・共有: Slackチャンネルで進捗状況を共有していることを伝え、普段からのコミュニケーションをアピールしています。
1. 助けを求める際、必要な人を巻き込む: メンターとチームリーダーに相談したことを伝え、周囲の協力を得ようとする姿勢を示しています。
1. 自然と感謝の言葉を口にする: 質問の最後に感謝の言葉を述べ、丁寧なコミュニケーションを心がけています
