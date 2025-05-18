---
title: 🗂 Javaコレクション入門：ポケモンと日常業務で学ぼう！ListとMapとSetの使い分け具体例
tags: Java入門 list setup map
author: nakamoto
slide: false
---
# 🗂 Javaコレクション入門：ポケモンと日常業務で学ぼう！


## 🔰 目次


1.  [配列（Array）とリスト（List）の違い](#配列（Array）とリスト（List）の違い)

   * 配列（Array)は入れ物の大きさが固定
   * リスト（List)は入れ物の大きさが変更可能
1. [List（順番を大事にしたいとき）](#list)

   * ポケモンの例：手持ちポケモンの順番
   * 実務の例：注文の順番管理
2. [Set（重複を避けたいとき）](#set)

   * ポケモンの例：図鑑登録（重複しない）
   * 実務の例：メールアドレスの重複登録防止
3. [Map（名前から情報を取り出したいとき）](#map)

   * ポケモンの例：タイプ別ポケモン表
   * 実務の例：社員IDからプロフィール管理

---

## 配列（Array）とリスト（List）の違い

![ChatGPT_arraylist.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/969a3471-2124-4876-9363-c192e9e6a0e6.png)


### 🔹 配列（Array）

* **「入れ物の大きさが最初から決まっている」**
* 一度決めた数（例：6匹）から増やすことはできない
* でも、**動きは速い**し、ポケモンの種類を決めておけば使いやすい

#### ✅ ポケモンの例

ポケモンバトル用の「手持ちポケモン」は6匹まで。
つまり「6匹分だけの箱＝配列」です。途中で7匹目は入れられません。

#### ✅ 実務の例

毎日決まった人数の生徒（例：30人分）の出席番号リストを作るとき。
毎日同じ人数なら配列で管理すると効率的です。

---

### 🔸 List（リスト）

* **「あとから追加も削除もできる入れ物」**
* データの数が増えたり減ったりしても大丈夫
* その分、ちょっと動きは遅め。でも**便利な機能がたくさんついてる！**

#### ✅ ポケモンの例

ポケモン牧場（ボックス）にポケモンをどんどん預けたり引き出したりできる。
→ この「自由に出し入れできるボックス」がList！

#### ✅ 実務の例

買い物リストや、アンケートの回答者名簿。
途中で人が増えたり減ったりする場合はListで管理すると簡単です。

---

### 🎓 まとめ

|        | 配列（Array）     | List（リスト）  |
| ------ | ------------- | ---------- |
| サイズ変更  | ❌できない（固定）     | ✅できる（柔軟）   |
| 操作の自由度 | 少ない（単純）       | 多い（便利）     |
| 向いてる場面 | 数が決まっているもの    | 数が増減するもの   |
| ポケモン例  | 手持ちポケモン（6匹固定） | ボックス（預け放題） |
| 実務例    | 出席番号表         | 買い物リスト     |

---

### Javaコレクションの全体像

![GPTListSetMap.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/39256/ec24b59c-f0ce-404b-82f0-98489840b7bd.png)


```
┌────────────────────────────────────────────┐
│                Collection系                │
│  List（順番あり・重複OK）                │
│  Set（順番なしまたは制御可能・重複NG）    │
└────────────────────────────────────────────┘
┌────────────────────────┐
│         Map系           │
│  KeyとValueのペア       │
└────────────────────────┘
```

---

## ✅ List（リスト）

| 特徴      | 内容                              |
| ------- | ------------------------------- |
| 順序      | **保持される（追加した順番に取り出せる）**         |
| 重複要素    | **許容される（同じ要素を複数入れられる）**         |
| 主な実装クラス | `ArrayList`, `LinkedList`       |
| 主な用途    | 「順番通りに並べたい」「同じデータを複数扱いたい」場面に適する |

**例えるなら…**
ポケモンのパーティ（6匹）は順番が重要で、同じポケモン（ピカチュウ）を何匹も並べることもできます。
→ このように「順番」と「重複」が許されるのがList。

---

## ✅ Set（セット）

| 特徴      | 内容                                    |
| ------- | ------------------------------------- |
| 順序      | **基本は保持されないが、実装によって制御可能**             |
| 重複要素    | **許容されない（同じ要素は1つまで）**                 |
| 主な実装クラス | `HashSet`, `LinkedHashSet`, `TreeSet` |
| 主な用途    | 「重複をなくして1つずつ扱いたい」「集合演算をしたい」場合に便利      |

**例えるなら…**
ポケモン図鑑。1種類のポケモン（例えばピカチュウ）は**1回登録されれば十分**。
→ どれだけ捕まえても「1匹」としてカウントされるようなイメージ。

| 実装クラス           | 特徴                |
| --------------- | ----------------- |
| `HashSet`       | 順番なし・高速           |
| `LinkedHashSet` | **追加順を保持**        |
| `TreeSet`       | **自然順や指定順に自動ソート** |

---

## ✅ Map（マップ）

| 特徴      | 内容                                    |
| ------- | ------------------------------------- |
| 順序      | **基本は保持されないが、実装により制御可能**              |
| 重複キー    | **許容されない（Keyは一意）**                    |
| 重複値     | **許容される（Valueは重複OK）**                 |
| 主な実装クラス | `HashMap`, `LinkedHashMap`, `TreeMap` |
| 主な用途    | 「Key（鍵）でデータにアクセスしたい」場合に必須             |

**例えるなら…**
ポケモンの名前をキー、対応する進化レベルをバリューにする「進化辞典」。
例：ピカチュウ → 進化Lv.22、ヒトカゲ → 進化Lv.16 のように
→ 「ポケモン名」というキーで、情報を高速に探せるのがMap。

| 実装クラス           | 特徴                     |
| --------------- | ---------------------- |
| `HashMap`       | 順番なし・高速                |
| `LinkedHashMap` | **追加順を保持**             |
| `TreeMap`       | **キー順にソート（自然順または比較器）** |

---

## 🔁 比較表まとめ

|       | List      | Set      | Map             |
| ----- | --------- | -------- | --------------- |
| 順序    | あり        | なし（制御可）  | なし（制御可）         |
| 重複の扱い | 許容        | **NG**   | KeyはNG／ValueはOK |
| 主な使い方 | パーティ, 並べる | 図鑑, 重複除去 | 辞書, IDと情報のペア管理  |

---



## 🟡 List

### 🎮 ポケモンの例：手持ちポケモンの順番

```java
import java.util.*;

public class PokemonListExample {
    public static void main(String[] args) {
        List<String> pokemonParty = new ArrayList<>();
        pokemonParty.add("ピカチュウ");
        pokemonParty.add("リザードン");
        pokemonParty.add("カメックス");

        for (int i = 0; i < pokemonParty.size(); i++) {
            System.out.println((i + 1) + "番目のポケモン：" + pokemonParty.get(i));
        }
    }
}
```

🟨 **出力例**

```
1番目のポケモン：ピカチュウ  
2番目のポケモン：リザードン  
3番目のポケモン：カメックス  
```

---

### 🏢 実務の例：注文の順番管理

```java
import java.util.*;

public class OrderListExample {
    public static void main(String[] args) {
        List<String> orderList = new ArrayList<>();
        orderList.add("牛丼");
        orderList.add("味噌汁");
        orderList.add("サラダ");

        System.out.println("注文された商品：");
        for (int i = 0; i < orderList.size(); i++) {
            System.out.println((i + 1) + "番目：" + orderList.get(i));
        }
    }
}
```

🟨 **出力例**

```
注文された商品：  
1番目：牛丼  
2番目：味噌汁  
3番目：サラダ  
```


---

## 🔴 Set

### 🎮 ポケモンの例：図鑑登録（重複しない・順番保証なし）

```java
import java.util.*;

public class PokemonSetExample {
    public static void main(String[] args) {
        Set<String> pokedex = new HashSet<>();

        pokedex.add("ピカチュウ");
        pokedex.add("ピカチュウ"); // 無視される
        pokedex.add("カビゴン");
        pokedex.add("フシギダネ");

        System.out.println("図鑑に登録されたポケモン：");
        for (String name : pokedex) {
            System.out.println("- " + name);
        }
    }
}
```

🔺 **出力例1（順序はランダム）**

```
図鑑に登録されたポケモン：  
- フシギダネ  
- ピカチュウ  
- カビゴン  
```

🔺 **出力例2（順序はランダム）**

```
図鑑に登録されたポケモン：  
- ピカチュウ
- フシギダネ    
- カビゴン  
```

---

### 🏢 実務の例：メールアドレス登録（重複チェック）

```java
import java.util.*;

public class EmailSetExample {
    public static void main(String[] args) {
        Set<String> registeredEmails = new HashSet<>();
        registeredEmails.add("test@example.com");
        registeredEmails.add("hello@example.com");

        String inputEmail = "test@example.com";

        if (registeredEmails.contains(inputEmail)) {
            System.out.println("このメールアドレスはすでに登録されています。");
        } else {
            registeredEmails.add(inputEmail);
            System.out.println("登録が完了しました！");
        }
    }
}
```

🔺 **出力例**

```
このメールアドレスはすでに登録されています。
```

---

## 🟠 Map

### 🎮 ポケモンの例：タイプ別ポケモン表（Map + List）

```java
import java.util.*;

public class PokemonMapListExample {
    public static void main(String[] args) {
        Map<String, List<String>> typeToPokemons = new HashMap<>();

        typeToPokemons.put("でんき", Arrays.asList("ピカチュウ", "ライチュウ", "エモンガ"));
        typeToPokemons.put("ほのお", Arrays.asList("ヒトカゲ", "リザードン", "ブースター"));

        for (String type : typeToPokemons.keySet()) {
            System.out.println("【" + type + "タイプ】");
            for (String pokemon : typeToPokemons.get(type)) {
                System.out.println(" - " + pokemon);
            }
        }
    }
}
```

🟧 **出力例**

```
【でんきタイプ】  
 - ピカチュウ  
 - ライチュウ  
 - エモンガ  
【ほのおタイプ】  
 - ヒトカゲ  
 - リザードン  
 - ブースター  
```

---

### 🏢 実務の例：社員IDからプロフィール管理（Map + クラス）

```java
import java.util.*;

class Employee {
    String name;
    String department;

    Employee(String name, String department) {
        this.name = name;
        this.department = department;
    }
}

public class EmployeeMapExample {
    public static void main(String[] args) {
        Map<String, Employee> employeeData = new HashMap<>();
        employeeData.put("B002", new Employee("田中太郎", "経理部"));
        employeeData.put("A001", new Employee("佐藤花子", "営業部"));

        String id = "B002";
        Employee e = employeeData.get(id);
        System.out.println("社員ID：" + id);
        System.out.println("名前：" + e.name);
        System.out.println("所属：" + e.department);
    }
}
```

🟧 **出力例**

```
社員ID：B002  
名前：田中太郎  
所属：経理部  
```


---


## 🧠 まとめ

| コレクション | ポケモンの例       | 実務の例           | 特徴          |
| ------ | ------------ | -------------- | ----------- |
| List   | 手持ちポケモンの順番   | 商品注文の順番        | 順番あり・重複OK   |
| Map    | タイプ別のポケモン表   | 社員IDからの情報管理    | キーと値のセット    |
| Set    | 図鑑に登録されたポケモン | 登録メールアドレスの重複排除 | 重複NG・順番保証なし |


## 更にコレクションを学習したい方向け

https://qiita.com/nakamoto/items/aa01e120f09895982417

https://qiita.com/nakamoto/items/cce39f6b1f89d61d83c8
