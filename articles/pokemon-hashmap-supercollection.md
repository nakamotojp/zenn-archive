---
title: 🧩 Java中級コレクション編：ポケモンと実務で学ぶ便利な使い方7選(hashmap LinkedHashSet TreeMap Collections Comparable Comparator Steam API)
tags: HashMap LinkedHashSet TreeMap Collections Comparable
author: nakamoto
slide: false
---

# 🧩 Java中級コレクション編：ポケモンと実務で学ぶ便利な使い方7選

---

## 🔰 目次

1. [HashMapを使う場合](#1-hashmapを使う場合)
2. [LinkedHashSetで順番保証付きのSet](#2-linkedhashsetで順番保証付きのset)
3. [TreeMapでキー順ソートされるMap](#3-treemapでキー順ソートされるmap)
4. [Collectionsを使う場合](#4-collectionsを使う場合)
5. [自然順序付けでのソートする場合（Comparable）](#5-自然順序付けでのソートする場合-comparable)
6. [Comparatorを使う場合](#6-comparatorを使う場合)
7. [Stream APIを使う場合](#7-stream-apiを使う場合)

---

## 1. HashMapを使う場合

### 🎮 ポケモンの例：ポケモンと技の対応表

```java
// ======================================
// 1. HashMap：高速アクセス・順番保証なし
// ======================================

// 🧢 ポケモンの例：ポケモンと技
import java.util.*;

public class HashMapExample {
    public static void main(String[] args) {
        // ポケモンの名前をキーにして、覚えている技をバリューに登録
        Map<String, String> moveMap = new HashMap<>();
        moveMap.put("ピカチュウ", "10まんボルト");
        moveMap.put("リザードン", "かえんほうしゃ");
        moveMap.put("カビゴン", "のしかかり");

        // ピカチュウがどんな技を持っているか調べる
        System.out.println("ピカチュウの技：" + moveMap.get("ピカチュウ"));
    }
}
```

🟨 **出力例**

```
ピカチュウの技：10まんボルト
```

### 🛒 実務例：商品コードと商品名の対応表

```java
// 🛒 実務例：商品コードと商品名の対応表
import java.util.*;

public class ProductHashMap {
    public static void main(String[] args) {
        // 商品コードをキーに、商品名をバリューに
        Map<String, String> productMap = new HashMap<>();
        productMap.put("A001", "りんご");
        productMap.put("B002", "バナナ");

        // 商品コードA001の名前を出力
        System.out.println("A001の商品は：" + productMap.get("A001"));
    }
}


```
🟨 **出力例**

```
A001の商品は：りんご
```
---

## 2. LinkedHashSetで順番保証付きのSet

### 🎮 ポケモンの例：ジムバッジの入手順

```java
// ===================================================
// 2. LinkedHashSet：重複NG・順番保持
// ===================================================

// 🏅 ポケモンの例：ジムバッジの取得順
import java.util.*;

public class LinkedHashSetExample {
    public static void main(String[] args) {
        // ジムリーダーの名前を登録（順番あり・重複なし）
        Set<String> badges = new LinkedHashSet<>();
        badges.add("タケシ");
        badges.add("カスミ");
        badges.add("マチス");

        // 取得順に出力
        for (String badge : badges) {
            System.out.println("バッジ：" + badge);
        }
    }
}
```

🟧 **出力例**

```
バッジ：タケシ  
バッジ：カスミ  
バッジ：マチス  
```

### 🧾 実務例：訪問順の顧客記録

```java
// ===================================================
// 2. LinkedHashSet：重複NG・順番保持
// ===================================================

// 🧾 実務例：訪問順の顧客記録
import java.util.*;

public class ClientVisitExample {
    public static void main(String[] args) {
        // 訪問した顧客の名前（順番を記録）
        Set<String> clients = new LinkedHashSet<>();
        clients.add("山田商事");
        clients.add("田中建設");
        clients.add("佐藤製作所");

        for (String name : clients) {
            System.out.println("訪問先：" + name);
        }
    }
}
```

🟧 **出力例**

```
訪問先：山田商事
訪問先：田中建設
訪問先：佐藤製作所
```

---

## 3. TreeMapでキー順ソートされるMap

### 🎮 ポケモンの例：ポケモンの図鑑番号と名前

```java
// ===================================================
// 3. TreeMap：キー順ソート自動
// ===================================================

// 📚 ポケモンの例：図鑑番号とポケモン名
import java.util.*;

public class TreeMapExample {
    public static void main(String[] args) {
        // 図鑑番号（キー）で自動的にソートされる
        Map<Integer, String> pokedex = new TreeMap<>();
        pokedex.put(25, "ピカチュウ");
        pokedex.put(6, "リザードン");
        pokedex.put(1, "フシギダネ");

        for (Map.Entry<Integer, String> entry : pokedex.entrySet()) {
            System.out.println(entry.getKey() + "番：" + entry.getValue());
        }
    }
}

```

🟩 **出力例**

```
1番：フシギダネ  
6番：リザードン  
25番：ピカチュウ  
```

### 📊 実務例：社員IDと名前を昇順で表示

```java
// ===================================================
// 3. TreeMap：キー順ソート自動
// ===================================================

// 📊 実務例：社員IDと名前を昇順で表示
import java.util.*;

public class EmployeeTreeMap {
    public static void main(String[] args) {
        Map<String, String> employees = new TreeMap<>();
        employees.put("E003", "高橋");
        employees.put("E001", "佐藤");
        employees.put("E002", "田中");

        for (String id : employees.keySet()) {
            System.out.println("社員ID: " + id + " 氏名: " + employees.get(id));
        }
    }
}

```

🟩 **出力例**

```
社員ID: E001 氏名: 佐藤
社員ID: E002 氏名: 田中
社員ID: E003 氏名: 高橋
```

---

## 4. Collectionsを使う場合（ソートやシャッフル）

### 🎲 ポケモンの例：技をランダムに選ぶ

```java
// ===================================================
// 4. Collectionsユーティリティ：シャッフルや並べ替え
// ===================================================

// 🎲 ポケモンの例：技をランダムに選ぶ
import java.util.*;

public class CollectionsShuffleExample {
    public static void main(String[] args) {
        List<String> moves = Arrays.asList("10まんボルト", "でんこうせっか", "アイアンテール");
        Collections.shuffle(moves); // リストの順番をランダムに
        System.out.println("選ばれた技: " + moves.get(0));
    }
}

```

🟪 **出力例**

```
選ばれた技：10まんボルト（※毎回ランダム）
```

### 🍀 実務例：抽選で当選者を決める

```java
// ===================================================
// 4. Collectionsユーティリティ：シャッフルや並べ替え
// ===================================================

// 🍀 実務例：抽選で当選者を決める
import java.util.*;

public class LotteryExample {
    public static void main(String[] args) {
        List<String> users = Arrays.asList("山田", "田中", "佐藤", "高橋");
        Collections.shuffle(users);
        System.out.println("当選者は: " + users.get(0));
    }
}

```

🟪 **出力例**

```
当選者は: 佐藤
```

---

## 5. 自然順序付けでのソートする場合（Comparable）

### 🎮 ポケモンの例：ポケモン名を五十音順で並べ替え

```java
// ===================================================
// 5. Comparable：自然順序での並べ替え
// ===================================================

// 🎮 ポケモンの例：ポケモン名を五十音順で並べ替え
import java.util.*;

public class SortPokemonExample {
    public static void main(String[] args) {
        List<String> pokemons = Arrays.asList("ピカチュウ", "フシギダネ", "カビゴン");
        Collections.sort(pokemons); // 自然順（文字列の昇順）
        for (String name : pokemons) {
            System.out.println(name);
        }
    }
}
```

🟨 **出力例**

```
カビゴン  
ピカチュウ  
フシギダネ  
```


### 📂 実務例：商品名をアルファベット順で並べる

```java
// ===================================================
// 5. Comparable：自然順序での並べ替え
// ===================================================

// 📂 実務例：商品名をアルファベット順で並べる
import java.util.*;

public class ProductSortExample {
    public static void main(String[] args) {
        List<String> items = Arrays.asList("Apple", "Banana", "Carrot");
        Collections.sort(items);
        for (String item : items) {
            System.out.println(item);
        }
    }
}
```

🟨 **出力例**

```
Apple
Banana
Carrot
```


---

## 6. Comparatorを使う場合

### 🧮 実務例：ポケモンの文字数で並べる

```java
// ===================================================
// 6. Comparator：独自ルールでソート
// ===================================================

// 🧮 実務例：ポケモンの文字数で並べる
import java.util.*;

public class NameLengthSortExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("ピカチュー", "ピチュー", "パモ");
        names.sort(Comparator.comparingInt(String::length));
        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

🟥 **出力例**

```
パモ
ピチュー 
ピカチュー
```

### 🧮 実務例：顧客名の文字数で並べる

```java
// ===================================================
// 6. Comparator：独自ルールでソート
// ===================================================

// 🧮 実務例：顧客名の文字数で並べる
import java.util.*;

public class NameLengthSortExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("佐藤", "田中太郎", "鈴木一郎");
        names.sort(Comparator.comparingInt(String::length));
        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

🟥 **出力例**

```
佐藤  
鈴木一郎  
田中太郎  
```


---

## 7. Stream APIを使う場合

### 🎮 ポケモンの例：HP100以上のポケモンだけを抽出

```java
// ===================================================
// 7. Stream API：絞り込み・集計・加工など
// ===================================================

// 🎮 ポケモンの例：HP100以上のポケモンだけを抽出
import java.util.*;
import java.util.stream.*;

class Pokemon {
    String name;
    int hp;
    Pokemon(String name, int hp) {
        this.name = name;
        this.hp = hp;
    }
}

public class StreamPokemonExample {
    public static void main(String[] args) {
        List<Pokemon> team = Arrays.asList(
            new Pokemon("ピカチュウ", 90),
            new Pokemon("リザードン", 120),
            new Pokemon("カビゴン", 160)
        );

        team.stream()
            .filter(p -> p.hp >= 100) // HP100以上を抽出
            .forEach(p -> System.out.println(p.name + "（HP: " + p.hp + "）"));
    }
}

```

🟦 **出力例**

```
リザードン（HP: 120）
カビゴン（HP: 160）  
```


### 🏢 実務例：時給1000円以上のスタッフだけを抽出

```java
// ===================================================
// 7. Stream API：絞り込み・集計・加工など
// ===================================================

// 🏢 実務例：時給1000円以上のスタッフだけを抽出
import java.util.*;
import java.util.stream.*;

class Staff {
    String name;
    int wage;
    Staff(String name, int wage) {
        this.name = name;
        this.wage = wage;
    }
}

public class StreamStaffExample {
    public static void main(String[] args) {
        List<Staff> staffList = Arrays.asList(
            new Staff("山田", 950),
            new Staff("田中", 1200),
            new Staff("佐藤", 1050)
        );

        staffList.stream()
            .filter(s -> s.wage >= 1000)
            .forEach(s -> System.out.println(s.name + "（時給: " + s.wage + "円）"));
    }
}
```

🟦 **出力例**

```
田中（時給: 1200円）
佐藤（時給: 1050円）
```

---

## 🧠 まとめ

| 機能・API        | 主な用途            | 特徴              |
| ------------- | --------------- | --------------- |
| HashMap       | 素早く情報取得したいとき    | 高速アクセス・順番保証なし   |
| LinkedHashSet | 順番も大切な重複なし集合    | 重複NG・順番保持       |
| TreeMap       | キー順で自動ソートしたいとき  | キー順ソート自動        |
| Collections   | ソート・シャッフルなど便利機能 | ユーティリティ系メソッドが豊富 |
| Comparable    | 自然順（文字・数値）ソート   | 自然順序（例：あいうえお順）  |
| Comparator    | 独自ルールで並べ替えたい    | 柔軟なカスタムソート      |
| Stream API    | 絞り込み・集計・加工      | 宣言的でスマートに操作可能   |


