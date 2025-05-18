---
title: 🏆【完全保存版・全12問】ポケモンで学ぶJavaオブジェクト指向クラス設計入門：継承・オーバーライド・進化・レベルアップまで完全攻略！
tags: マイクラ ポケモン Java入門 クラス
author: nakamoto
slide: false
---
# 🔍 クラス実装問題集逆引き目次（クラス実装問題：ポケモン編）

- 🔹 [ポケモンクラスの基本実装](#1-ポケモン継承なし例)
- 🔹 [ポケモンクラスの継承（LegendaryPokemon）](#2-ポケモン継承あり例)
- 🔹 [オーバーライドでTrainer情報追加](#3-ポケモン継承とoverrideあり例)
- 🔹 [インターフェースの実装（Displayable）](#4-ポケモン継承とoverrideとインターフェイスあり例)
- 🔹 [進化メソッド evolve() の追加](#1-ポケモンクラスに進化メソッドevolveを追加)
- 🔹 [if文・for文・配列を使った技習得処理](#2-ポケモンクラスにif文とfor文と配列を利用した処理を追加)
- 🔹 [Pikachuクラスの実装（Pokemonを継承）](#3-ポケモンクラスからピカチュウクラスを継承)
- 🔹 [Raichuクラスの実装（Pikachuを継承）](#4-ピカチュウクラスからライチュウクラスを継承)
- 🔹 [Eeveeクラスの実装（Pokemonを継承）](#5-ポケモンクラスからイーブイクラスを継承)
- 🔹 [Squirtleクラスの実装（Pokemonを継承）](#6-ポケモンクラスからゼニガメクラスを継承)
- 🔹 [Pokemonクラスのレベル機能リファクタリング](#7-ポケモンクラス自体をリファクタリングして機能追加)
- 🔹 [リファクタリングによるサブクラスへの影響](#8-継承したクラスが7-のリファクタリングでどのような影響を受けたか説明)


## 🔹 1. ポケモン継承なし例

## ✅ Pokemon クラスの作成

以下の仕様に従って `Pokemon` クラスを作成してください。

### フィールド

- `name`（型: String）: ポケモンの名前
- `type`（型: String）: ポケモンのタイプ

### メソッド

- `getName()` : 名前を返す
- `setName(String name)` : 名前を設定する
- `getType()` : タイプを返す
- `setType(String type)` : タイプを設定する
- `getInfo()` : `"Pikachu (Electric)"` のような形式で `name` と `type` を出力する文字列を返す

---

## 🖨 出力例

### 入力値
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
System.out.println(p.getInfo());
```

### 出力値
```
Pikachu (Electric)
```

---

## ✅ 解答コード例
```java
public class Pokemon {
    private String name;
    private String type;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public String getInfo() {
        return name + " (" + type + ")";
    }
}
```

## 🔹 2. ポケモン継承あり例

## ✅ Pokemon クラス

- 前問と同じ仕様

## ✅ LegendaryPokemon クラスの作成

`Pokemon` クラスを継承した `LegendaryPokemon` クラスを作成してください。

### フィールド

- `region`（型: String）: 発見された地方名（例: "Kanto"）

### メソッド

- `getRegion()` : 地方名を返す
- `setRegion(String region)` : 地方名を設定する
- `getInfo()` : `"Pikachu (Electric) - Region: Kanto"` のように `Pokemon` の情報に地域名を追加した形式で返す

---

## 🖨 出力例

### 入力値
```java
LegendaryPokemon lp = new LegendaryPokemon();
lp.setName("Pikachu");
lp.setType("Electric");
lp.setRegion("Kanto");
System.out.println(lp.getInfo());
```

### 出力値
```
Pikachu (Electric) - Region: Kanto
```

---

## ✅ 解答コード例
```java
public class LegendaryPokemon extends Pokemon {
    private String region;

    public String getRegion() {
        return region;
    }

    public void setRegion(String region) {
        this.region = region;
    }

    @Override
    public String getInfo() {
        return super.getInfo() + " - Region: " + region;
    }
}
```

## 🔹 3. ポケモン継承とOverrideあり例

## ✅ TrainerPokemon クラスの作成

`Pokemon` クラスを継承した `TrainerPokemon` クラスを作成してください。

### フィールド

- `trainerName`（型: String）: トレーナーの名前

### メソッド

- `getTrainerName()` / `setTrainerName(String trainerName)`
- `getInfo()` をオーバーライドし、`"[Ash] Pikachu (Electric)"` の形式で返す

---

## 🖨 出力例

### 入力値
```java
TrainerPokemon tp = new TrainerPokemon();
tp.setName("Pikachu");
tp.setType("Electric");
tp.setTrainerName("Ash");
System.out.println(tp.getInfo());
```

### 出力値
```
[Ash] Pikachu (Electric)
```

---

## ✅ 解答コード例
```java
public class TrainerPokemon extends Pokemon {
    private String trainerName;

    public String getTrainerName() {
        return trainerName;
    }

    public void setTrainerName(String trainerName) {
        this.trainerName = trainerName;
    }

    @Override
    public String getInfo() {
        return "[" + trainerName + "] " + super.getInfo();
    }
}
```

## 🔹 4. ポケモン継承とOverrideとインターフェイスあり例

## ✅ Displayable インターフェイス

- `display()` メソッドを定義する

## ✅ BattlePokemon クラスの作成

`Pokemon` を継承し、`Displayable` インターフェイスを実装する `BattlePokemon` クラスを作成してください。

### フィールド

- `level`（型: int）: レベル

### メソッド

- `getLevel()` / `setLevel(int level)`
- `getInfo()` をオーバーライドし、`"Pikachu (Electric) - Lv.25"` の形式で返す
- `display()` メソッドを実装し、`"Displaying: Pikachu"` を出力する

---

## 🖨 出力例

### 入力値
```java
BattlePokemon bp = new BattlePokemon();
bp.setName("Pikachu");
bp.setType("Electric");
bp.setLevel(25);
System.out.println(bp.getInfo());
bp.display();
```

### 出力値
```
Pikachu (Electric) - Lv.25
Displaying: Pikachu
```

---

## ✅ 解答コード例
```java
public interface Displayable {
    void display();
}

public class BattlePokemon extends Pokemon implements Displayable {
    private int level;

    public int getLevel() {
        return level;
    }

    public void setLevel(int level) {
        this.level = level;
    }

    @Override
    public String getInfo() {
        return super.getInfo() + " - Lv." + level;
    }

    @Override
    public void display() {
        System.out.println("Displaying: " + getName());
    }
}
```

---

# 🧩 クラス追加実装問題集（ポケモン編）

## 🔹 1. ポケモンクラスに、進化メソッド(evolve)を追加

## ✅ Pokemon クラスの拡張

以下の仕様に従って、`Pokemon` クラスに `evolve()` メソッドを追加してください。

### 既存フィールド

- `name`（型: String）: ポケモンの名前
- `type`（型: String）: ポケモンのタイプ

### 追加メソッド

- `evolve(String newName)`  
  - 引数で渡された `newName` を使って名前を進化後の名前に変更します  
  - 変更後の名前とタイプを `"進化後: Raichu (Electric)"` のように表示する形式で `System.out.println()` で出力します。

---

## 🖨 出力例

### 入力値
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
p.evolve("Raichu");
```

### 出力値
```
進化後: Raichu (Electric)
```

---

## ✅ 解答コード例
```java
public class Pokemon {
    // ポケモンの名前
    private String name;
    // ポケモンのタイプ
    private String type;

    // 名前を取得するメソッド
    public String getName() {
        return name;
    }

    // 名前を設定するメソッド
    public void setName(String name) {
        this.name = name;
    }

    // タイプを取得するメソッド
    public String getType() {
        return type;
    }

    // タイプを設定するメソッド
    public void setType(String type) {
        this.type = type;
    }

    // ポケモンの情報を表示するメソッド
    public String getInfo() {
        return name + " (" + type + ")";
    }

    // ポケモンを進化させるメソッド
    // 引数で新しい名前を受け取り、名前を変更し、進化後の情報を表示する
    public void evolve(String newName) {
        this.name = newName; // 名前を新しい名前に変更
        System.out.println("進化後: " + getInfo()); // 変更後の情報を出力
    }
}
```

---

# 🧩 クラス追加実装問題集（追加クラス実装）


## 🔹 2. ポケモンクラスに、if文とfor文と配列を利用した処理を追加

## ✅ Pokemon クラスの拡張

以下の仕様に従って、`Pokemon` クラスに `learnMoves(String[] moves)` メソッドを追加してください。

### 新規メソッド

- `learnMoves(String[] moves)`
  - ポケモンが覚える技の一覧を表示します。
  - 配列 `moves` に含まれる各技名を順番に出力します。
  - 配列が `null` または空の場合は `"覚える技がありません"` と出力してください。

---

## 🖨 出力例

### 入力値
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
String[] moves = {"Thunderbolt", "Quick Attack", "Iron Tail"};
p.learnMoves(moves);
```

### 出力値
```
Pikachu が覚える技:
- Thunderbolt
- Quick Attack
- - Iron Tail
```

---

## ✅ 解答コード例
```java
public class Pokemon {
    private String name;
    private String type;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public String getInfo() {
        return name + " (" + type + ")";
    }

    // 技を覚える処理。if文とfor文と配列の使い方を確認するメソッド
    public void learnMoves(String[] moves) {
        // 技が何も指定されていない場合
        if (moves == null || moves.length == 0) {
            System.out.println("覚える技がありません");
            return;
        }

        // 技がある場合、それぞれを順番に表示
        System.out.println(name + " が覚える技:");
        for (String move : moves) {
            System.out.println("- " + move); // 各技名を表示
        }
    }
}
```

---

## 🔹 3. ポケモンクラスから、ピカチュウクラスを継承

## ✅ Pikachu クラスの作成

- `Pokemon` クラスを継承し、名前を `"Pikachu"`、タイプを `"Electric"` に初期設定するコンストラクタを作成してください。

---

## 🖨 出力例

### 入力値
```java
Pikachu pika = new Pikachu();
System.out.println(pika.getInfo());
```

### 出力値
```
Pikachu (Electric)
```

---

## ✅ 解答コード例
```java
public class Pikachu extends Pokemon {

    // Pikachu 固有のコンストラクタ。名前とタイプを自動設定
    public Pikachu() {
        setName("Pikachu");   // 名前を"Pikachu"に設定
        setType("Electric");  // タイプを"Electric"に設定
    }
}
```

---

## 🔹 4. ピカチュウクラスから、ライチュウクラスを継承

## ✅ Raichu クラスの作成

- `Pikachu` クラスを継承し、名前を `"Raichu"` に上書きするコンストラクタを作成してください。

---

## 🖨 出力例

### 入力値
```java
Raichu r = new Raichu();
System.out.println(r.getInfo());
```

### 出力値
```
Raichu (Electric)
```

---

## ✅ 解答コード例
```java
public class Raichu extends Pikachu {

    // Raichu コンストラクタ。親クラス Pikachu のタイプを継承しつつ名前を変更
    public Raichu() {
        setName("Raichu"); // 名前を"Raichu"に設定（タイプはElectricのまま）
    }
}
```

---

## 🔹 5. ポケモンクラスから、イーブイクラスを継承

## ✅ Eevee クラスの作成

- `Pokemon` クラスを継承し、名前を `"Eevee"`、タイプを `"Normal"` に設定するコンストラクタを作成してください。

---

## 🖨 出力例

### 入力値
```java
Eevee e = new Eevee();
System.out.println(e.getInfo());
```

### 出力値
```
Eevee (Normal)
```

---

## ✅ 解答コード例
```java
public class Eevee extends Pokemon {

    // Eeveeのコンストラクタで初期設定を行う
    public Eevee() {
        setName("Eevee");     // 名前を"Eevee"に設定
        setType("Normal");    // タイプを"Normal"に設定
    }
}
```

---

## 🔹 6. ポケモンクラスから、ゼニガメクラスを継承

## ✅ Squirtle クラスの作成

- `Pokemon` クラスを継承し、名前を `"Squirtle"`、タイプを `"Water"` に設定するコンストラクタを作成してください。

---

## 🖨 出力例

### 入力値
```java
Squirtle s = new Squirtle();
System.out.println(s.getInfo());
```

### 出力値
```
Squirtle (Water)
```

---

## ✅ 解答コード例
```java
public class Squirtle extends Pokemon {

    // Squirtleのコンストラクタで初期値を設定する
    public Squirtle() {
        setName("Squirtle");  // 名前を"Squirtle"に設定
        setType("Water");     // タイプを"Water"に設定
    }
}
```

---

## 🔹 7. ポケモンクラス自体をリファクタリングして機能追加

## ✅ Pokemon クラスのリファクタリング

- 以下のフィールドとメソッドを追加してください。

### フィールド追加

- `level`（型: int）: ポケモンのレベル（初期値は1）

### メソッド追加

- `getLevel()` / `setLevel(int level)`
- `levelUp()` : レベルを1上げて `"Pikachuのレベルが2になった！"` のように出力する

---

## 🖨 出力例

### 入力値
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
p.setLevel(5);
p.levelUp();
System.out.println(p.getLevel());
```

### 出力値
```
Pikachuのレベルが6になった！
6
```

---

## ✅ 解答コード例
```java
public class Pokemon {
    private String name;
    private String type;
    private int level = 1; // レベルの初期値は1

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public String getInfo() {
        return name + " (" + type + ")";
    }

    // レベルを取得する
    public int getLevel() {
        return level;
    }

    // レベルを設定する
    public void setLevel(int level) {
        this.level = level;
    }

    // レベルアップ処理を行う
    public void levelUp() {
        level += 1; // レベルを1上げる
        System.out.println(name + "のレベルが" + level + "になった！");
    }
}
```

---

## 🔹 8. 継承したクラスが、7. のリファクタリングでどのような影響を受けたか説明

## ✅ 影響内容の説明

### ポイント

- `Pokemon` クラスに `level` フィールドと `levelUp()` メソッドが追加されたことで、**すべてのサブクラス（Pikachu, Raichu, Eevee, Squirtleなど）** も自動的にレベルの管理ができるようになりました。
- 例えば、`Raichu` クラスのインスタンスに対して `setLevel(10)` や `levelUp()` を使うことが可能になります。
- これにより、**コードの再利用性**が向上し、各進化ポケモンが共通の成長ロジックを持つことができます。

### 例：
```java
Raichu r = new Raichu();
r.setLevel(10);
r.levelUp(); // => Raichuのレベルが11になった！
```

---

## ✅ メリットまとめ

- レベルの一括管理が基底クラスで可能に
- サブクラスは何も変更せずともレベル機能を自動的に継承
- メソッド追加時に影響範囲を最小限に抑えた設計ができる
