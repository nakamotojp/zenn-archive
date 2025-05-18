---
title:  포켓몬 육성과 같이 오브젝트 지향을 가족으로 배울 수 있는 Java 초클래스 입문 ~"좋아"가 배움으로 바뀌는 마법의 도감~
tags: 객체지향 클래스 Java 중학수험 포켓몬
author: nakamoto
slide: false
---
# 📚 목차

- 🔹 [제1장 포켓몬 도감 만들기! 클래스 설계도](#제1장-포켓몬-도감-만들기-클래스-설계도)
- 🔹 [1.1 오브젝트란?](#11-오브젝트란)
- 🔹 [1.2 클래스를 만들자](#12-클래스를-만들자)
- 🔹 [1.3 정리와 테스트](#13-정리와-테스트)
- 🔹 [제2장 몬스터볼에서 GET! 인스턴스 생성과 사용법](#제2장-몬스터볼에서-get-인스턴스-생성과-사용법)
- 🔹 [2.1 인스턴스를 만들자](#21-인스턴스를-만들자)
- 🔹 [2.2 게터와 세터의 사용법](#22-게터와-세터의-사용법)
- 🔹 [2.3 메서드를 추가하자](#23-메서드를-추가하자)
- 🔹 [2.4 정리와 테스트](#24-정리와-테스트)
- 🔹 [제3장 포켓몬의 비밀을 지켜라! 클래스의 구조](#제3장-포켓몬의-비밀을-지켜라-클래스의-구조)
- 🔹 [3.1 다른 클래스에서의 접근 제한](#31-다른-클래스에서의-접근-제한)
- 🔹 [3.2 멤버의 구조](#32-멤버의-구조)
- 🔹 [3.3 생성자의 구조](#33-생성자의-구조)
- 🔹 [3.4 정리와 테스트](#34-정리와-테스트)
- 🔹 [제4장 포켓몬을 가리켜라! 인스턴스와 참조의 비밀](#제4장-포켓몬을-가리켜라-인스턴스와-참조의-비밀)
- 🔹 [4.1 참조란?](#41-참조란)
- 🔹 [4.2 참조를 의식하자](#42-참조를-의식하자)
- 🔹 [4.3 완전히 불변의 클래스를 만들자!](#43-완전히-불변의-클래스를-만들자)
- 🔹 [4.4 참조형](#44-참조형)
- 🔹 [4.5 정리와 테스트](#45-정리와-테스트)
- 🔹 [제5장 오리지널 포켓몬 설계하기! 객체 모델링](#제5장-오리지널-포켓몬-설계하기-객체-모델링)
- 🔹 [5.1 기능을 구현하는 클래스](#51-기능을-구현하는-클래스)
- 🔹 [5.2 record](#52-record)
- 🔹 [5.3 정리와 테스트](#53-정리와-테스트)
- 🔹 [제6장 진화의 비밀을 밝혀라! 상속이라는 혈통](#제6장-진화의-비밀을-밝혀라-상속이라는-혈통)
- 🔹 [6.1 클래스 다이어그램](#61-클래스-다이어그램)
- 🔹 [6.2 상속](#62-상속)
- 🔹 [6.3 상속 규칙](#63-상속-규칙)
- 🔹 [6.4 정리와 테스트](#64-정리와-테스트)
- 🔹 [제7장 포켓몬 가계의 미스터리! 상속 관계를 마스터하자](#제7장-포켓몬-가계의-미스터리-상속-관계를-마스터하자)
- 🔹 [7.1 상속 트리](#71-상속-트리)
- 🔹 [7.2 생성자의 연결](#72-생성자의-연결)
- 🔹 [7.3 여러 클래스를 하나의 파일로](#73-여러-클래스를-하나의-파일로)
- 🔹 [7.4 protected 한정자](#74-protected-한정자)
- 🔹 [7.5 정리와 테스트](#75-정리와-테스트)
- 🔹 [제8장 포켓몬의 변신술! 참조의 자동 형변환](#제8장-포켓몬의-변신술-참조의-자동-형변환)
- 🔹 [8.1 참조의 자동 형변환](#81-참조의-자동-형변환)
- 🔹 [8.2 업캐스트와 다운캐스트](#82-업캐스트와-다운캐스트)
- 🔹 [8.3 instanceof 연산자](#83-instanceof-연산자)
- 🔹 [8.4 switch에 의한 타입 판정](#84-switch에-의한-타입-판정)
- 🔹 [8.5 정리와 테스트](#85-정리와-테스트)
- 🔹 [제9장 하나의 기술로 다양한 효과! 다형성](#제9장-하나의-기술로-다양한-효과-다형성)
- 🔹 [9.1 오버로드](#91-오버로드)
- 🔹 [9.2 오버라이드](#92-오버라이드)
- 🔹 [9.3 다형성](#93-다형성)
- 🔹 [9.4 정리와 테스트](#94-정리와-테스트)
- 🔹 [제10장 환상의 포켓몬의 수수께끼! 추상 클래스의 세계](#제10장-환상의-포켓몬의-수수께끼-추상-클래스의-세계)
- 🔹 [10.1 추상 클래스란?](#101-추상-클래스란)
- 🔹 [10.2 추상 클래스 상속](#102-추상-클래스-상속)
- 🔹 [10.3 추상 클래스 다이어그램](#103-추상-클래스-다이어그램)
- 🔹 [10.4 정리와 테스트](#104-정리와-테스트)
- 🔹 [제11장 포켓몬의 타입과 능력! 인터페이스의 힘](#제11장-포켓몬의-타입과-능력-인터페이스의-힘)
- 🔹 [11.1 인터페이스란](#111-인터페이스란)
- 🔹 [11.2 인터페이스형으로의 형변환](#112-인터페이스형으로의-형변환)
- 🔹 [11.3 인터페이스에 의한 다형성](#113-인터페이스에-의한-다형성)
- 🔹 [11.4 인터페이스 상속](#114-인터페이스-상속)
- 🔹 [11.5 정리와 테스트](#115-정리와-테스트)

---

# 🧩 제1장 포켓몬 도감 만들기! 클래스 설계도

## 🎯 1.1 오브젝트란?

### 🌟 포켓몬도 오브젝트? 실생활에서 느끼는 객체지향의 세계

포켓몬 세계에서 피카츄나 파이리 같은 모든 포켓몬은 '오브젝트'입니다.  
현실 세계로 예를 들면, '자전거'나 '스마트폰'도 오브젝트입니다.  

오브젝트에는 두 가지 요소가 있습니다：

- 🧬 **속성 (필드)**: 예를 들어 피카츄의 '타입', '레벨' 등
- 🛠 **행동 (메서드)**: 피카츄가 사용하는 '10만 볼트'나 '울음소리' 같은 기술

---

## 🏗 1.2 클래스를 만들자

### 📘 도감에 싣기 전에! 클래스라는 설계도의 중요성

클래스란 '오브젝트의 설계도'입니다.  
예를 들어 '포켓몬'이라는 클래스를 만들면, 이를 바탕으로 피카츄, 파이리 등 다양한 포켓몬 오브젝트를 만들 수 있습니다.

---

### 🛠 클래스 정의 예시 (Java)

```java
public class Pokemon {
    String name; // 포켓몬 이름
    String type; // 타입 (예: 전기)
    int level;   // 레벨

    public void introduce() {
        System.out.println("안녕! 나는 " + name + ", 타입은 " + type + ", 레벨은 " + level + "이야!");
    }
}
```

---

## 🧪 1.3 정리와 테스트

### ✅ 클래스의 핵심 정리

| 요소 | 설명 |
|------|------|
| 클래스 | 설계도 (포켓몬의 공통 정보) |
| 오브젝트 | 실제로 생성된 피카츄나 파이리 등 |
| 속성 | 이름, 타입, 레벨 |
| 메서드 | 자기소개 등의 행동 |

---

### 📝 연습문제

1. 자신만의 포켓몬을 생각해서 `Pokemon` 클래스로 표현해 보세요.
2. `introduce()` 메서드에 '사용 가능한 기술'도 소개할 수 있도록 확장해 보세요.



---

# 🎯 제2장 몬스터볼에서 GET! 인스턴스 생성과 사용법

## 🧱 2.1 인스턴스를 만들자

### 🥚 포켓몬을 소환하라! new 연산자와 생성자의 마법

Java에서는 `new` 키워드를 사용하여 클래스에서 오브젝트(인스턴스)를 생성합니다.  
이것은 마치 몬스터볼에서 포켓몬을 꺼내는 것과 같습니다.

```java
Pokemon pika = new Pokemon();
```

- `Pokemon`: 설계도(클래스)의 이름
- `pika`: 생성된 피카츄 인스턴스
- `new Pokemon()`: 새로운 포켓몬을 만드는 마법의 주문

---

## 🔓 2.2 게터와 세터의 사용법

### 🔍 "너의 HP는 몇이야?" 게터로 상태 확인

```java
public String getName() {
    return name;
}
```

### 💪 "레벨 업!" 세터로 포켓몬을 강화하자

```java
public void setLevel(int lvl) {
    level = lvl;
}
```

**게터와 세터를 사용하는 이유는?**  
-> **캡슐화(encapsulation)** 를 활용하기 위해서입니다.

---

## 🧬 캡슐화란?

> 클래스 내부 데이터를 외부에서 직접 변경하지 못하게 막고, 안전하게 다루는 방법

### ❌ 잘못된 예 (캡슐화 안됨)

```java
public class Pokemon {
    public int hp;
}
...
pikachu.hp = -100; // 위험한 직접 접근!
```

### ✅ 올바른 예 (게터와 세터 사용)

```java
public class Pokemon {
    private int hp;

    public void setHp(int hp) {
        if (hp >= 0) {
            this.hp = hp;
        } else {
            System.out.println("HP는 0 이상이어야 합니다.");
        }
    }

    public int getHp() {
        return this.hp;
    }
}
```

---

## 🛠 2.3 메서드를 추가하자

### ⚡ "10만 볼트!" 기술을 사용하는 메서드

```java
public void useMove() {
    System.out.println(name + "의 " + move + "! 효과는 굉장했다!");
}
```

---

## ✅ 고급편: @Override 와 toString

```java
@Override
public String toString() {
    return "포켓몬: " + name + " / 타입: " + type + " / 레벨: " + level + " / 기술: " + move;
}
```

**@Override는 필수는 아니지만, 매우 권장됩니다.**

---

## 🎯 2.4 정리와 테스트

| 용어 | 설명 |
|------|------|
| 인스턴스 | new 연산자로 만든 객체 |
| 게터 | 값을 읽는 메서드 |
| 세터 | 값을 설정하는 메서드 |
| @Override | 부모 클래스 메서드를 재정의할 때 사용 |
| toString | 객체 정보를 문자열로 출력 |

---

### 💻 최종 예시 코드

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
        System.out.println(name + "의 " + move + "! 효과는 굉장했다!");
    }

    @Override
    public String toString() {
        return "포켓몬: " + name + " / 타입: " + type + " / 레벨: " + level + " / 기술: " + move;
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika = new Pokemon();
        pika.setName("피카츄");
        pika.setType("전기");
        pika.setLevel(25);
        pika.setMove("10만 볼트");

        System.out.println(pika);
        pika.useMove();
    }
}
```

🧩 이 예시로 클래스 → 인스턴스 생성 → 값 설정 → 메서드 실행의 흐름을 체험할 수 있습니다!


---


# 🛡 제3장 포켓몬의 비밀을 지켜라! 클래스의 구조

## 🔐 3.1 다른 클래스에서의 접근 제한

### 🧳 "그 HP는 보여줄 수 없어!" private와 public의 경계선

```java
public class Pokemon {
    private int hp;

    public int getHp() {
        return hp;
    }

    public void setHp(int hp) {
        this.hp = hp;
    }
}
```

📝 `private`은 비공개, `public`은 공개를 의미합니다.

---

### 🧩 회색 지대 속성! 아무 것도 안 썼을 때의 세계

접근 제한자를 생략하면 동일한 패키지 내에서는 접근 가능합니다. 이를 **default 접근**이라고 부릅니다.

---

### 🛡 비밀스러운 스테이터스를 보호하라! 캡슐화의 진수

**캡슐화(encapsulation)**는 데이터를 클래스 안에 감추고 외부에서 직접 접근을 막는 개념입니다.  
포켓몬 게임에서 상태창을 트레이너만 조작할 수 있는 것처럼요!

---

## ⚙️ 3.2 멤버의 구조

### ⚡ "모든 포켓몬의 공통 특성" static 멤버의 힘

```java
public class Pokemon {
    public static final int MAX_LEVEL = 100;
}
```

📝 `static`은 클래스 전체에서 공유되는 변수 또는 메서드를 의미합니다.

---

### 🧬 "이 피카츄만의 특성" 인스턴스 멤버의 개성

```java
public class Pokemon {
    private int level; // 인스턴스마다 개별 보유
}
```

---

### ⚠️ static과 instance, 공존 가능할까?

가능합니다. 차이를 명확히 이해하는 것이 중요합니다.

```java
public class Pokemon {
    public static final int MAX_LEVEL = 100;
    private int level;

    public boolean isMaxLevel() {
        return level == MAX_LEVEL;
    }
}
```

---

## 🧱 3.3 생성자의 구조

### 🌀 같은 이름, 다른 방식? 오버로딩의 마법

```java
public Pokemon() {
    this.name = "피카츄";
}

public Pokemon(String name) {
    this.name = name;
}
```

---

### 🌈 "컬러풀 포켓몬" 다양한 생성자 만들기

```java
public Pokemon(String name, int level, String type) {
    this.name = name;
    this.level = level;
    this.type = type;
}
```

---

### 🔁 this()로 생성자 연결하기

```java
public Pokemon(String name, int level) {
    this(name, level, "노말");
}
```

---

### 🧊 아무 것도 지정하지 않아도 생기는 포켓몬?

생성자를 정의하지 않으면 Java가 자동으로 기본 생성자를 생성해줍니다.  
하지만 다른 생성자가 정의되어 있으면 기본 생성자는 자동 생성되지 않으므로 주의!

---

## 🧪 3.4 정리와 테스트

### 📘 3장 요약: 캡슐화와 멤버 관리 핵심

| 항목 | 내용 |
|------|------|
| 접근 제한자 | 데이터 노출 여부 설정 |
| private | 외부에서 볼 수 없음 |
| public | 어디서나 사용 가능 |
| static | 모든 포켓몬 공통 특성 |
| 생성자 | 포켓몬 생성 시 초기 설정 메서드 |
| this | 자기 자신을 가리킴, 생성자 호출 가능 |

---

### 🎮 테스트 코드

```java
public class Pokemon {
    private String name;
    private String type;
    private int level;
    public static final int MAX_LEVEL = 100;

    public Pokemon() {
        this("피카츄", 5, "전기");
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
        System.out.println("나는 " + name + "! 타입: " + type + ", 레벨: " + level);
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika = new Pokemon();
        pika.introduce();

        Pokemon eve = new Pokemon("이브이", 10, "노말");
        eve.introduce();

        System.out.println("이브이는 최대 레벨인가? " + eve.isMaxLevel());
    }
}
```

🧩 이 예시로 캡슐화, static 변수, 생성자 오버로딩을 체험할 수 있습니다!


---

# 🧭 제4장 포켓몬을 가리켜라! 인스턴스와 참조의 비밀

## 🎯 4.1 참조란?

### 🎈 몬스터볼과 포켓몬의 관계? 참조의 신비한 역할

Java에서 `참조(reference)`란 오브젝트의 **위치(주소)**를 저장하는 변수입니다.  
몬스터볼은 포켓몬을 담는 그릇이죠. Java에서는 이 몬스터볼이 참조입니다.

```java
Pokemon pika1 = new Pokemon(); // 포켓몬 생성
Pokemon pika2 = pika1;         // pika1과 같은 포켓몬을 가리킴
```

📝 `pika2`는 `pika1`과 **같은 포켓몬 인스턴스**를 참조할 뿐, 새로 생성된 것이 아닙니다.

---

## 👀 4.2 참조를 의식하자

### 🧪 "복사했는데 같은 포켓몬?" 변수 간 대입의 진실

```java
pika2.setLevel(50);
System.out.println(pika1.getLevel()); // 50이 출력됨
```

📌 오브젝트는 **복사되는 것이 아니라 참조 주소만 전달**되는 것이 기본입니다.

---

## 🧊 4.3 완전히 불변의 클래스를 만들자

### 🧼 "전설의 포켓몬, 아무도 바꿀 수 없다!" 완전 불변 구현

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

🛡 모든 필드에 `final`을 붙이면 **값이 한 번 정해지면 변경 불가**한 클래스가 됩니다.

---

## 🧬 4.4 참조형

### 🧪 "기본형과의 차이는?" Java의 타입 시스템

| 타입 종류 | 예시 | 특징 |
|----------|------|------|
| 기본형 (primitive) | int, double | 값 자체를 저장 |
| 참조형 (reference) | String, Pokemon | 객체의 주소를 저장 |

---

### ⚠️ "비어있는 몬스터볼?" null의 정체

```java
Pokemon pika = null;
pika.introduce(); // NullPointerException!
```

🚨 `null`은 아직 객체가 생성되지 않은 상태를 의미하며, 사용 시 에러 발생!

---

## 🧪 4.5 정리와 테스트

### 🧾 4장 요약: 참조와 불변 이해

| 키워드 | 설명 |
|--------|------|
| 참조 | 객체의 위치를 가리킴 |
| 같은 참조 | 변수 대입 시 같은 객체를 가리킴 |
| null | 아무 것도 없는 상태 |
| 불변 (immutable) | 값이 절대 변경되지 않는 설계 |

---

### 💻 종합 테스트 코드

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
        System.out.println("나는 " + name + "! 타입: " + type + ", 레벨: " + level);
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon pika1 = new Pokemon("피카츄", "전기", 25);
        Pokemon pika2 = pika1; // 동일 참조

        pika1.introduce();
        pika2.introduce();

        // 아래 코드는 NullPointerException을 발생시킴
        // Pokemon empty = null;
        // empty.introduce();
    }
}
```

🔍 이 예시로 참조 개념과 null 위험성을 직접 체험할 수 있습니다!



---

# 🧪 제5장 오리지널 포켓몬을 설계하라! 오브젝트 모델링

## 🧱 5.1 기능을 구현하는 클래스

### 📝 어떤 포켓몬을 만들까? 전체적인 구조를 생각해보자

포켓몬 게임에서는 이름, 타입, 레벨, 기술 등 다양한 정보가 필요합니다.  
이 정보를 클래스로 어떻게 표현할지를 생각하는 것이 바로 **오브젝트 모델링**입니다.

---

### 🧮 "특성과 기술을 정하자" 클래스 정의 예시

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
        System.out.println("이름: " + name + " / 타입: " + type + " / 레벨: " + level);
        System.out.println("기술 목록:");
        for (String move : moves) {
            System.out.println("- " + move);
        }
    }
}
```

---

### 🚀 "정말 이대로 괜찮을까?" 설계 검토 포인트

- 기술은 몇 개까지 허용할까? → 배열로 유연하게 대응
- 레벨 상한은? → `static final` 사용
- 여러 타입 지원? → 이번엔 단일 타입만 사용

---

### ⚙️ 구현 시작! 클래스 → 코드 변환

```java
String[] fushiMoves = {"몸통 박치기", "덩굴채찍", "독가루"};
Pokemon fushi = new Pokemon("이상해씨", "풀", 10, fushiMoves);
fushi.introduce();
```

---

## 📦 5.2 record

### 🆕 Java 16 신기능! record는 누구인가?

Java 16부터는 `record`로 간단한 데이터 클래스를 정의할 수 있습니다.

```java
public record SimplePokemon(String name, String type, int level) {}
```

---

### ✨ "간편 도감 등록" record의 장점

- 생성자
- getter
- toString()
- equals()

이 모든 기능이 자동으로 생성됩니다.

```java
SimplePokemon zenigame = new SimplePokemon("꼬부기", "물", 8);
System.out.println(zenigame.name());
System.out.println(zenigame);
```

---

### 🧠 기능 확장도 가능

```java
public record SimplePokemon(String name, String type, int level) {
    public boolean isStarter() {
        return level <= 10;
    }
}
```

---

### 🔒 전설 포켓몬은 변하지 않는다! 불변 record

`record`의 필드는 모두 `final`이므로 수정 불가능.  
뮤츠나 루기아 같은 전설의 포켓몬에 적합한 구조입니다.

---

### 🪄 3줄로 포켓몬 만들기!

```java
SimplePokemon hitokage = new SimplePokemon("파이리", "불꽃", 5);
System.out.println("팀 후보: " + hitokage.name());
```

---

## 🎯 5.3 정리와 테스트

### ✅ 모델링과 record 요약

| 개념 | 설명 |
|------|------|
| 모델링 | 현실의 개체를 프로그램 구조로 설계 |
| 필드 | 이름, 타입, 기술 등 정보 |
| 메서드 | 소개, 기술 사용 등 동작 |
| record | 간단한 불변 데이터 클래스 |
| 불변 | 값이 절대 바뀌지 않는 구조 |

---

### 💻 종합 예제 코드

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
        System.out.println("이름: " + name + " / 타입: " + type + " / 레벨: " + level);
        System.out.println("기술:");
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
        String[] moves = {"몸통 박치기", "덩굴채찍", "독가루"};
        Pokemon bulbasaur = new Pokemon("이상해씨", "풀", 10, moves);
        bulbasaur.introduce();

        SimplePokemon charmander = new SimplePokemon("파이리", "불꽃", 5);
        System.out.println("팀 후보: " + charmander.name());
        System.out.println("스타터? " + charmander.isStarter());
    }
}
```

🧩 이 예시로 클래스와 record를 활용한 데이터 정의를 모두 경험할 수 있습니다!


---
# 🧬 제6장 진화의 비밀을 밝혀라! 상속이라는 혈통

## 📊 6.1 클래스 다이어그램

### 📚 "포켓몬 도감의 뒷면" 클래스 다이어그램 해독법

Java의 상속은 도감의 진화 트리와 유사합니다.  
예) 피츄 → 피카츄 → 라이츄

```
Pokemon (부모 클래스)
  └── Pikachu (자식 클래스)
       └── Raichu (손자 클래스)
```

📝 공통 정보는 부모 클래스에, 진화하면서 생기는 속성은 자식 클래스에 작성합니다.

---

## 🧪 6.2 상속

### 👪 "피츄에서 피카츄로!" 클래스 확장하기

```java
public class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("나는 " + name + ", 타입은 " + type + "!");
    }
}

public class Pikachu extends Pokemon {
    int level;

    public void thunderbolt() {
        System.out.println(name + "의 10만 볼트!");
    }
}
```

📝 Pikachu는 Pokemon을 상속받아 `level`과 `thunderbolt`를 추가합니다.

---

### 🐣 "부화 과정" 생성자 호출 순서

```java
public class Pokemon {
    public Pokemon() {
        System.out.println("포켓몬이 태어났다!");
    }
}

public class Pikachu extends Pokemon {
    public Pikachu() {
        System.out.println("피카츄가 태어났다!");
    }
}
```

출력 순서:

```
포켓몬이 태어났다!
피카츄가 태어났다!
```

---

### 🚀 상속 효과 실감하기

```java
Pikachu pika = new Pikachu();
pika.name = "피카츄";
pika.type = "전기";
pika.level = 15;

pika.introduce();     // 부모 메서드
pika.thunderbolt();   // 자식 메서드
```

---

## 📜 6.3 상속 규칙

### 🧠 "○○은 ○○이다" Is-a 관계

"피카츄는 포켓몬이다" → 상속 가능  
"포켓몬은 피카츄이다" → ❌ 역상속 불가

---

### 🚫 "전설은 복제 불가!" 상속 금지 클래스

```java
public final class Mewtwo extends Pokemon {
    // 상속 불가 클래스
}
```

📝 `final` 클래스는 더 이상 상속할 수 없습니다.

---

### 🔒 "봉인된 특성" Sealed 클래스 (Java 17+)

```java
public sealed class Pokemon permits Pikachu, Eevee {}
```

`Pokemon`은 Pikachu와 Eevee만 상속 가능

---

### 🧙 "전수된 기술" 상속 불가 멤버

- `private` 필드/메서드 → 자식 클래스에서 접근 불가
- `final` 메서드 → 오버라이드 불가

---

## 🎯 6.4 정리와 테스트

### 📘 상속 요약

| 개념 | 설명 |
|------|------|
| 상속 (extends) | 클래스 기능을 이어받음 |
| 부모 클래스 | 공통 기능 보유 |
| 자식 클래스 | 개별 기능 추가 |
| Is-a 관계 | ○○는 ××이다 |
| final | 상속 금지 |
| sealed | 상속 가능한 클래스 제한 (Java 17+) |

---

### 💻 종합 예제 코드

```java
public class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("나는 " + name + ", 타입은 " + type + "!");
    }
}

public class Pikachu extends Pokemon {
    int level;

    public Pikachu(String name, int level) {
        this.name = name;
        this.type = "전기";
        this.level = level;
    }

    public void thunderbolt() {
        System.out.println(name + "의 10만 볼트! 효과는 굉장했다!");
    }
}

public class Main {
    public static void main(String[] args) {
        Pikachu pika = new Pikachu("피카츄", 20);
        pika.introduce();
        pika.thunderbolt();
    }
}
```

🧩 이 예제로 상속, 생성자 호출 순서, 메서드 오버라이드의 흐름을 익힐 수 있습니다!


---

# 🌳 제7장 포켓몬 가계의 미스터리! 상속 관계를 마스터하라

## 🧭 7.1 상속 트리

### 🧬 "포켓몬 진화 가계도" 상속 트리 전체 구조

포켓몬은 진화 계통을 가지며, Java에서도 **상속 트리**로 표현할 수 있습니다.

예) 나옹 → 나이킹 (지역 진화)

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

### 🧬 모든 포켓몬의 조상, Object 클래스

Java의 모든 클래스는 암묵적으로 `Object` 클래스를 상속합니다.

```java
public class Pikachu {
    // Object 클래스의 toString(), equals() 사용 가능
}
```

---

## 🔗 7.2 생성자의 연결

### 👶 부모 → 자식으로 이어지는 생성자 호출

```java
public class Pokemon {
    public Pokemon(String name) {
        System.out.println(name + " 이(가) 태어났습니다!");
    }
}

public class Eevee extends Pokemon {
    public Eevee() {
        super("이브이");
        System.out.println("이브이 준비 완료!");
    }
}
```

출력 결과:
```
이브이 이(가) 태어났습니다!
이브이 준비 완료!
```

---

### ❓ super() 생략 시 행동

부모 클래스에 인자가 없는 기본 생성자가 있으면 `super()`는 생략 가능  
단, **부모 생성자에 매개변수가 있다면 반드시 명시 필요!**

---

## 📁 7.3 여러 클래스를 하나의 파일에 정의하기

```java
public class Pokemon {
    String name;
    public void greet() {
        System.out.println("안녕! 나는 " + name + "!");
    }
}

class Pikachu extends Pokemon {
    public Pikachu() {
        name = "피카츄";
    }
}
```

📝 파일명이 `Pokemon.java`일 경우, public 클래스는 하나만 존재해야 하며 나머지는 public 없이 작성

---

## 🛡 7.4 protected 접근자

### 🏠 "가족에게만 보이는 특성" protected의 특별한 힘

```java
public class Pokemon {
    protected String name; // 같은 패키지와 자식 클래스에서 접근 가능
}
```

---

### ⚠️ 주의사항

- 외부 패키지에서는 접근 불가
- public, private와 구분하여 정확히 사용

---

### 🌐 접근 제어자 정리

| 접근자 | 동일 클래스 | 동일 패키지 | 자식 클래스 | 외부 클래스 |
|--------|-------------|-------------|-------------|-------------|
| public | ○           | ○           | ○           | ○           |
| protected | ○        | ○           | ○           | ×           |
| (default) | ○        | ○           | ×           | ×           |
| private | ○          | ×           | ×           | ×           |

---

## 🎯 7.5 정리와 테스트

### 🧾 7장 요약: Java의 상속 가계도 완전 이해!

| 개념 | 설명 |
|------|------|
| 상속 트리 | 클래스 간 부모-자식 구조 |
| Object 클래스 | 모든 클래스의 조상 |
| super() | 부모 생성자 호출 |
| protected | 같은 패키지, 자식 클래스 접근 가능 |

---

### 💻 종합 예제 코드

```java
public class Pokemon {
    protected String name;

    public Pokemon(String name) {
        this.name = name;
        System.out.println(name + " 이(가) 태어났습니다!");
    }

    public void greet() {
        System.out.println("안녕하세요! 저는 " + name + " 입니다!");
    }
}

class Pikachu extends Pokemon {
    public Pikachu() {
        super("피카츄");
        System.out.println("피카츄 준비 완료!");
    }

    public void thunderbolt() {
        System.out.println(name + " 의 10만 볼트!");
    }
}

public class Main {
    public static void main(String[] args) {
        Pikachu pika = new Pikachu();
        pika.greet();
        pika.thunderbolt();
    }
}
```

🎉 이 장에서는 상속 구조, protected, 클래스 파일 내 동시 정의 등을 모두 마스터할 수 있습니다!



---


# 🌀 제8장 포켓몬의 변신술! 참조의 자동 형변환

## 🪄 8.1 참조의 자동 형변환

### 🔁 "메타몽의 변신" 자식 → 부모 클래스 자동 형변환

Java에서는 자식 클래스의 인스턴스를 부모 클래스 타입으로 자동 형변환할 수 있습니다.

```java
Pokemon pika = new Pikachu("피카츄", 20);
pika.introduce(); // 부모 메서드는 사용 가능
```

📝 이처럼 `Pikachu` 타입 인스턴스를 `Pokemon` 타입으로 저장 → 업캐스팅

---

## 🧱 8.2 업캐스트와 다운캐스트

### ⬆️ 업캐스트 (자동)

```java
Pokemon poke = new Pikachu("피카츄", 20);
```

### ⬇️ 다운캐스트 (명시적)

```java
Pikachu pika = (Pikachu) poke;
pika.thunderbolt(); // 자식 클래스의 메서드 사용 가능
```

⚠️ `poke`가 Pikachu가 아닐 경우, `ClassCastException` 발생

---

## 🔍 8.3 instanceof 연산자

### 🧪 "진짜 피카츄인가?" instanceof로 타입 확인

```java
if (poke instanceof Pikachu) {
    Pikachu pika = (Pikachu) poke;
    pika.thunderbolt();
}
```

📝 안전한 다운캐스트를 위한 타입 체크 필수

---

## 🧠 8.4 switch를 이용한 타입 판별 (Java 14~)

```java
switch (poke) {
    case Pikachu p -> p.thunderbolt();
    case Eevee e -> e.adapt();
    default -> System.out.println("알 수 없는 포켓몬");
}
```

📝 패턴 매칭 switch를 활용하면 코드가 간결해집니다

---

## 🎯 8.5 정리와 테스트

### 📘 변신의 기술 요약

| 용어 | 설명 |
|------|------|
| 업캐스트 | 자식 → 부모 (자동) |
| 다운캐스트 | 부모 → 자식 (명시적) |
| instanceof | 타입 안전 확인 |
| switch 패턴 | Java 14+ 타입 분기 가능 |

---

### 💻 종합 예제 코드

```java
public class Pokemon {
    protected String name;

    public Pokemon(String name) {
        this.name = name;
    }

    public void introduce() {
        System.out.println("나는 " + name + " 입니다!");
    }
}

class Pikachu extends Pokemon {
    private int level;

    public Pikachu(String name, int level) {
        super(name);
        this.level = level;
    }

    public void thunderbolt() {
        System.out.println(name + " 의 10만 볼트! 레벨: " + level);
    }
}

class Eevee extends Pokemon {
    public Eevee(String name) {
        super(name);
    }

    public void adapt() {
        System.out.println(name + " 는 다양한 타입으로 진화할 수 있다!");
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon poke1 = new Pikachu("피카츄", 25); // 업캐스트
        Pokemon poke2 = new Eevee("이브이");

        if (poke1 instanceof Pikachu) {
            Pikachu pika = (Pikachu) poke1;
            pika.thunderbolt();
        }

        switch (poke2) {
            case Pikachu p -> p.thunderbolt();
            case Eevee e -> e.adapt();
            default -> System.out.println("알 수 없는 포켓몬");
        }
    }
}
```

🧩 이 예제로 업캐스트, 다운캐스트, instanceof, switch 패턴을 마스터할 수 있습니다!


---

# 🎭 제9장 하나의 기술로 다양한 효과! 다형성(Polymorphism)

## 💡 9.1 오버로드

### 🧠 "같은 이름, 다른 효과" 오버로드의 원리

Java에서는 같은 이름의 메서드를 **매개변수의 수나 타입이 다르면** 여러 개 정의할 수 있습니다.

```java
public void attack(String move) {
    System.out.println("「" + move + "」을(를) 사용했다!");
}

public void attack(String move, int times) {
    System.out.println("「" + move + "」을(를) " + times + "번 연속 사용했다!");
}
```

---

## 🔁 9.2 오버라이드

### 🔄 "진화로 기술이 강화되었다!" 오버라이드의 개념

오버라이드는 **부모 클래스의 메서드를 자식 클래스에서 재정의**하는 것입니다.

```java
public class Pokemon {
    public void attack() {
        System.out.println("기본 공격!");
    }
}

public class Pikachu extends Pokemon {
    @Override
    public void attack() {
        System.out.println("피카츄의 10만 볼트!");
    }
}
```

📝 `@Override`는 재정의임을 명확히 하여 실수를 방지합니다.

---

## 🌀 9.3 다형성 (Polymorphism)

### 🎨 "같은 기술, 다른 효과" 다형성의 마법

다형성이란 **부모 클래스 타입으로 자식 클래스 메서드를 실행할 수 있는 기능**입니다.

```java
Pokemon poke = new Pikachu();
poke.attack(); // 실제로는 Pikachu의 attack() 실행됨
```

📝 호출 시점의 타입이 아닌 **실제 인스턴스 타입에 따라 동작** → 동적 바인딩

---

### ✨ 트레이너가 기술을 사용할 때

```java
public class Trainer {
    public void usePokemon(Pokemon p) {
        p.attack();
    }
}
```

포켓몬의 종류와 관계없이 `attack()` 호출 가능

---

## 🎯 9.4 정리와 테스트

### ✅ 다형성 요약 표

| 개념 | 설명 |
|------|------|
| 오버로드 | 같은 이름, 다른 인자 |
| 오버라이드 | 부모 메서드 재정의 |
| 다형성 | 부모 타입으로 자식 메서드 실행 |
| 동적 바인딩 | 실행 시점에 맞는 메서드 호출 |

---

### 💻 종합 예제 코드

```java
public class Pokemon {
    public void attack() {
        System.out.println("기본 공격!");
    }

    public void attack(String move) {
        System.out.println("「" + move + "」을(를) 사용했다!");
    }

    public void attack(String move, int times) {
        System.out.println("「" + move + "」을(를) " + times + "번 사용했다!");
    }
}

class Pikachu extends Pokemon {
    @Override
    public void attack() {
        System.out.println("피카츄의 10만 볼트!");
    }
}

class Eevee extends Pokemon {
    @Override
    public void attack() {
        System.out.println("이브이의 스피드스타!");
    }
}

class Trainer {
    public void usePokemon(Pokemon p) {
        p.attack();
    }
}

public class Main {
    public static void main(String[] args) {
        Trainer ash = new Trainer();

        Pokemon pika = new Pikachu();
        Pokemon eevee = new Eevee();

        ash.usePokemon(pika);   // 피카츄의 기술
        ash.usePokemon(eevee);  // 이브이의 기술

        pika.attack("아이언 테일");      // 오버로드 예시
        pika.attack("전광석화", 2);      // 오버로드 예시
    }
}
```

🧩 이 코드로 **오버로드, 오버라이드, 다형성** 전부를 실습할 수 있습니다!


---


# 🦄 제10장 환상의 포켓몬의 비밀! 추상 클래스의 세계

## 🧩 10.1 추상 클래스란?

### 👻 "도감에 없는 미지의 포켓몬" 추상 클래스의 정의

추상 클래스 (`abstract class`)는 **불완전한 설계도**입니다.  
직접 인스턴스화할 수 없으며, **자식 클래스에서 구현을 완성**해야 합니다.

```java
public abstract class Pokemon {
    String name;
    String type;

    public void introduce() {
        System.out.println("나는 " + name + "! 타입은 " + type + "!");
    }

    public abstract void specialMove(); // 추상 메서드
}
```

📝 추상 메서드는 몸체가 없으며, 반드시 자식 클래스에서 정의 필요

---

## 🧬 10.2 추상 클래스 상속

### 🌟 "전설에서 현실로" 추상 메서드 구현

```java
public class Mew extends Pokemon {
    public Mew() {
        name = "뮤";
        type = "에스퍼";
    }

    @Override
    public void specialMove() {
        System.out.println("뮤의 사이코키네시스!");
    }
}
```

📝 자식 클래스에서 반드시 `specialMove()`를 오버라이드 해야 함

---

### ✨ 중간 추상화 계층 만들기

```java
public abstract class LegendaryPokemon extends Pokemon {
    public abstract void summon(); // 추가 추상 메서드
}
```

---

## 🗺 10.3 추상 클래스 다이어그램

```
<<abstract>> Pokemon
    + introduce()
    + specialMove() ← abstract

       ▲
       |
     Mew (specialMove() 구현)
```

📝 `<<abstract>>`는 추상 클래스를 나타냅니다

---

## 🎯 10.4 정리와 테스트

### ✅ 요약 표

| 항목 | 설명 |
|------|------|
| abstract class | 불완전한 설계도, 직접 생성 불가 |
| abstract method | 자식 클래스에서 구현 필요 |
| 강제 구현 | 추상 메서드가 있으면 반드시 구현 |
| 중간 추상화 | 추상 클래스끼리도 상속 가능 |

---

### 💻 종합 예제 코드

```java
public abstract class Pokemon {
    protected String name;
    protected String type;

    public void introduce() {
        System.out.println("나는 " + name + "! 타입은 " + type + "!");
    }

    public abstract void specialMove();
}

class Mew extends Pokemon {
    public Mew() {
        this.name = "뮤";
        this.type = "에스퍼";
    }

    @Override
    public void specialMove() {
        System.out.println(name + "의 사이코키네시스!");
    }
}

public class Main {
    public static void main(String[] args) {
        Pokemon mystery = new Mew(); // 추상 클래스 타입으로 인스턴스 사용
        mystery.introduce();
        mystery.specialMove();
    }
}
```

🧩 이 예제로 **추상 클래스, 오버라이드, 다형성**까지 경험할 수 있습니다!


---


# 🔗 제11장 포켓몬의 타입과 능력! 인터페이스의 힘

## 💡 11.1 인터페이스란?

### 🔍 "비행 타입", "물 타입" → 인터페이스 정의

Java의 `interface`는 **기능의 계약서**입니다.  
공통된 능력을 여러 클래스가 구현할 수 있도록 합니다.

```java
public interface Flyable {
    void fly(); // 비행 타입이면 반드시 구현
}
```

---

### 🧪 "복수 타입을 가진 포켓몬" → 클래스에 인터페이스 구현

```java
public class Charizard implements Flyable {
    @Override
    public void fly() {
        System.out.println("리자몽이 하늘을 날았다!");
    }
}
```

📝 `implements` 키워드로 "이 클래스는 날 수 있다"고 명시

---

### ✨ 인터페이스 메서드는 모두 public abstract

즉, **수정 불가능하고 구현 강제됨**  
공통된 기능을 동일하게 사용하도록 설계된 구조

---

## 🔁 11.2 인터페이스 타입으로 형변환

### 🔄 "타입으로써의 포켓몬" 인터페이스 타입 사용

```java
Flyable flyingPokemon = new Charizard();
flyingPokemon.fly(); // 리자몽의 fly() 호출됨
```

---

### 🎯 "물 타입으로 사용" WaterType 예시

```java
public interface WaterType {
    void surf();
}

public class Vaporeon implements WaterType {
    @Override
    public void surf() {
        System.out.println("샤미드가 파도를 탄다!");
    }
}
```

---

## 🎭 11.3 인터페이스 기반 다형성

### 🧬 "같은 기술 이름, 다양한 클래스" 다형성 실현

```java
public void useFly(Flyable f) {
    f.fly();
}
```

📝 클래스와 무관하게 **Flyable 인터페이스만 구현되어 있으면 실행 가능**

---

### 🧪 "실전: 타입별 기술 효과"

```java
Flyable f1 = new Charizard();
Flyable f2 = new Pidgeot();

f1.fly(); // 리자몽
f2.fly(); // 피죤투
```

---

## 🌐 11.4 인터페이스 상속

### 🔗 "복합 타입 포켓몬" 다중 상속 구현

```java
public interface FlyingWaterType extends Flyable, WaterType {
    void dive();
}
```

---

### 🧠 인터페이스도 상속된다!

```java
public class Gyarados implements FlyingWaterType {
    @Override
    public void fly() {
        System.out.println("갸라도스가 날아올랐다!");
    }

    @Override
    public void surf() {
        System.out.println("갸라도스가 파도를 탔다!");
    }

    @Override
    public void dive() {
        System.out.println("갸라도스가 잠수했다!");
    }
}
```

---

## 🎯 11.5 정리와 테스트

### ✅ 요약 표

| 항목 | 설명 |
|------|------|
| interface | 기능 계약, 타입과 유사 |
| implements | 인터페이스 구현 |
| 다중 구현 | 여러 타입 동시 보유 가능 |
| 다형성 | 클래스 구분 없이 기능 호출 가능 |

---

### 💻 종합 예제 코드

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
        System.out.println("리자몽이 하늘을 날았다!");
    }
}

public class Vaporeon implements WaterType {
    @Override
    public void surf() {
        System.out.println("샤미드가 파도를 탔다!");
    }
}

public class Gyarados implements Flyable, WaterType {
    @Override
    public void fly() {
        System.out.println("갸라도스가 날아올랐다!");
    }

    @Override
    public void surf() {
        System.out.println("갸라도스가 파도를 쳤다!");
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
            water.surf(); // 갸라도스도 surf 가능
        }
    }
}
```

🧩 이 장에서는 **인터페이스, 다형성, 다중 구현**을 완전히 이해할 수 있습니다!
