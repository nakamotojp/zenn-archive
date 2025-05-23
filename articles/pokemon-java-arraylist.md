---
title: 🧠Java初学者向け：List・ArrayList・LinkedListの違いとポケモンで学ぶ使い分け
tags: LinkedList ArrayList Java入門 ポケモン
author: nakamoto
slide: false
---
# 🧠Java初学者向け：List・ArrayList・LinkedListの違いとポケモンで学ぶ使い分け

## 📌 目次

* はじめに
* List・ArrayList・LinkedListの違い
* 業務での使い分けアドバイス
* ポケモンを例にした使用シーンとコード解説

  * ArrayListを使うべき例
  * LinkedListを使うべき例
  * Listで柔軟に書く方法
* まとめ

---

## 🎓はじめに

Javaの`List`系コレクションは頻繁に登場しますが、「ArrayListとLinkedList、どっちを使えばいいの？」という疑問を抱く方も多いのではないでしょうか。

この記事では、初学者でもイメージしやすいポケモンを題材に、実際の使い分けをコード付きで解説していきます！

---

## 🗂️List・ArrayList・LinkedListの違い

| 特徴      | ArrayList     | LinkedList     |
| ------- | ------------- | -------------- |
| データ構造   | 配列ベース         | 連結リスト          |
| 挿入/削除   | 遅い（中間操作はO(n)） | 速い（O(1)）※位置による |
| 検索（get） | 速い（O(1)）      | 遅い（O(n)）       |
| メモリ効率   | 良い            | 悪い（オーバーヘッドあり）  |
| よく使う場面  | 要素数が多くない・検索中心 | 頻繁に挿入/削除する     |

---

## 💼業務での使い分けアドバイス

* **ArrayListが基本**：速度・使いやすさ・他の開発者との共通理解。
* **LinkedListは限定使用**：特定条件（大量の中間挿入/削除）でのみ使う。
* **List型で変数定義**：将来の実装変更に備えて柔軟に。

```java
// OKな例（柔軟性あり）
List<String> names = new ArrayList<>();
```

---

## 🧪ポケモンを例にした使用シーンとコード解説

### ✅ArrayListを使うべきケース：ポケモン図鑑

```java
import java.util.ArrayList;
import java.util.List;

public class PokemonDex {
    public static void main(String[] args) {
        // ポケモンの図鑑をArrayListで管理（検索が中心）
        List<String> pokedex = new ArrayList<>();
        pokedex.add("ピカチュウ");  // インデックス0に追加
        pokedex.add("ヒトカゲ");    // インデックス1に追加
        pokedex.add("ゼニガメ");    // インデックス2に追加

        // 図鑑番号から検索（検索が高速）
        System.out.println("2番目のポケモン: " + pokedex.get(1));
    }
}
```

📌**ArrayList向きの理由**：

* 図鑑は順番固定で頻繁な挿入削除がない。
* インデックスアクセスが高速（getがO(1)）。

---

### ✅LinkedListを使うべきケース：バトルの行動順

```java
import java.util.LinkedList;
import java.util.Queue;

public class BattleQueue {
    public static void main(String[] args) {
        // バトル中の行動順（キュー）をLinkedListで管理
        Queue<String> actionQueue = new LinkedList<>();

        actionQueue.offer("ピカチュウのこうげき");
        actionQueue.offer("ヒトカゲのこうげき");
        actionQueue.offer("ゼニガメのこうげき");

        // 行動を順に処理（先頭から取り出す）
        while (!actionQueue.isEmpty()) {
            System.out.println(actionQueue.poll()); // O(1)で取り出し
        }
    }
}
```

📌**LinkedList向きの理由**：

* キュー構造（FIFO）に適している。
* 頻繁に先頭から追加/削除するならLinkedListが高速。

---

### ⚖️Listを使って柔軟に書く

```java
import java.util.List;
import java.util.ArrayList;

public class PokemonTrainer {
    public static void main(String[] args) {
        // List型で宣言 → 実装を変更しやすい
        List<String> team = new ArrayList<>();
        team.add("ピカチュウ");
        team.add("フシギダネ");

        // 柔軟に拡張・削除なども可能
        team.remove("フシギダネ");
        team.add("カビゴン");

        System.out.println("現在の手持ちポケモン: " + team);
    }
}
```

💡**ポイント**：

* `List`型にしておけば、内部実装（ArrayList or LinkedList）を後で変更できる。

---

## 🔚まとめ

| 使用ケース                | 推奨クラス      | 理由            |
| -------------------- | ---------- | ------------- |
| 検索が中心（図鑑、一覧表示など）     | ArrayList  | getが高速        |
| 頻繁な挿入/削除（バトル、順番制御など） | LinkedList | add/removeが高速 |
| 実装を切り替える可能性がある       | Listで定義    | 柔軟性           |


---


