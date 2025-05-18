---
title: 🏆 [完整版 - 共 12 个问题] 使用 Pokémon 介绍 Java 面向对象类设计：继承、覆盖、演化和升级的完整指南！
tags: 面向对象类设计 pokemon Java入門
author: nakamoto
slide: false
---

## 🧭 目次（点击跳转）

- 🔹 [1. 不使用继承的宝可梦类示例](#-1-不使用继承的宝可梦类示例)
- 🔹 [2. 使用继承的宝可梦类示例](#-2-使用继承的宝可梦类示例)
- 🔹 [3. 使用继承与方法覆写（Override）的宝可梦类示例](#-3-使用继承与方法覆写override的宝可梦类示例)
- 🔹 [4. 使用继承、方法覆写和接口的宝可梦类示例](#-4-使用继承方法覆写和接口的宝可梦类示例)
- 🔹 [1. 为宝可梦类添加进化方法（evolve）](#-1-为宝可梦类添加进化方法evolve)
- 🔹 [2. 为宝可梦类添加使用 if 语句、for 循环和数组的处理](#-2-为宝可梦类添加使用-if-语句for-循环和数组的处理)
- 🔹 [3. 从宝可梦类继承皮卡丘类](#-3-从宝可梦类继承皮卡丘类)
- 🔹 [4. 从皮卡丘类继承雷丘类](#-4-从皮卡丘类继承雷丘类)
- 🔹 [5. 从宝可梦类继承伊布类](#-5-从宝可梦类继承伊布类)
- 🔹 [6. 从宝可梦类继承杰尼龟类](#-6-从宝可梦类继承杰尼龟类)
- 🔹 [7. 重构宝可梦类并添加新功能](#-7-重构宝可梦类并添加新功能)
- 🔹 [8. 说明继承类在第7项重构后的影响](#-8-说明继承类在第7项重构后的影响)



---

# 🔹 1. 不使用继承的宝可梦类示例

## ✅ 创建 Pokemon 类

请根据以下规格创建 `Pokemon` 类。

### 字段

- `name`（类型: String）: 宝可梦的名字  
- `type`（类型: String）: 宝可梦的属性  

### 方法

- `getName()` : 返回名字  
- `setName(String name)` : 设置名字  
- `getType()` : 返回属性  
- `setType(String type)` : 设置属性  
- `getInfo()` : 返回类似 `"Pikachu (Electric)"` 格式的包含名字和属性的字符串

---

## 🖨 输出示例

### 输入值
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
System.out.println(p.getInfo());
```

### 输出值
```
Pikachu (Electric)
```

---

## ✅ 示例代码
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

---

# 🔹 2. 使用继承的宝可梦类示例

## ✅ Pokemon 类

- 与上一题相同的规格

## ✅ 创建 LegendaryPokemon 类

请创建继承 `Pokemon` 类的 `LegendaryPokemon` 类。

### 字段

- `region`（类型: String）: 发现该宝可梦的地区名称（例："Kanto"）

### 方法

- `getRegion()` : 返回地区名称  
- `setRegion(String region)` : 设置地区名称  
- `getInfo()` : 返回格式为 `"Pikachu (Electric) - Region: Kanto"` 的字符串，将地区信息添加到 `Pokemon` 的信息中

---

## 🖨 输出示例

### 输入值
```java
LegendaryPokemon lp = new LegendaryPokemon();
lp.setName("Pikachu");
lp.setType("Electric");
lp.setRegion("Kanto");
System.out.println(lp.getInfo());
```

### 输出值
```
Pikachu (Electric) - Region: Kanto
```

---

## ✅ 示例代码
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

---

# 🔹 3. 使用继承与方法覆写（Override）的宝可梦类示例

## ✅ 创建 TrainerPokemon 类

请创建继承 `Pokemon` 类的 `TrainerPokemon` 类。

### 字段

- `trainerName`（类型: String）: 训练师的名字

### 方法

- `getTrainerName()` / `setTrainerName(String trainerName)`  
- 重写 `getInfo()` 方法，返回 `"[Ash] Pikachu (Electric)"` 的格式

---

## 🖨 输出示例

### 输入值
```java
TrainerPokemon tp = new TrainerPokemon();
tp.setName("Pikachu");
tp.setType("Electric");
tp.setTrainerName("Ash");
System.out.println(tp.getInfo());
```

### 输出值
```
[Ash] Pikachu (Electric)
```

---

## ✅ 示例代码
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

---

# 🔹 4. 使用继承、方法覆写和接口的宝可梦类示例

## ✅ Displayable 接口

- 定义 `display()` 方法

## ✅ 创建 BattlePokemon 类

请创建一个继承 `Pokemon` 类并实现 `Displayable` 接口的 `BattlePokemon` 类。

### 字段

- `level`（类型: int）: 等级

### 方法

- `getLevel()` / `setLevel(int level)`  
- 重写 `getInfo()`，返回 `"Pikachu (Electric) - Lv.25"` 的格式  
- 实现 `display()` 方法，输出 `"Displaying: Pikachu"`

---

## 🖨 输出示例

### 输入值
```java
BattlePokemon bp = new BattlePokemon();
bp.setName("Pikachu");
bp.setType("Electric");
bp.setLevel(25);
System.out.println(bp.getInfo());
bp.display();
```

### 输出值
```
Pikachu (Electric) - Lv.25
Displaying: Pikachu
```

---

## ✅ 示例代码
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

# 🔹 1. 为宝可梦类添加进化方法（evolve）

## ✅ 扩展 Pokemon 类

请根据以下规格，在 `Pokemon` 类中添加 `evolve()` 方法。

### 已有字段

- `name`（类型: String）: 宝可梦的名字  
- `type`（类型: String）: 宝可梦的属性

### 新增方法

- `evolve(String newName)`  
  - 使用传入的参数 `newName` 将名字更改为进化后的名称  
  - 以 `"进化后: Raichu (Electric)"` 的格式，通过 `System.out.println()` 输出进化后的名称和属性

---

## 🖨 输出示例

### 输入值
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
p.evolve("Raichu");
```

### 输出值
```
进化后: Raichu (Electric)
```

---

## ✅ 示例代码
```java
public class Pokemon {
    // 宝可梦的名字
    private String name;
    // 宝可梦的属性
    private String type;

    // 获取名字的方法
    public String getName() {
        return name;
    }

    // 设置名字的方法
    public void setName(String name) {
        this.name = name;
    }

    // 获取属性的方法
    public String getType() {
        return type;
    }

    // 设置属性的方法
    public void setType(String type) {
        this.type = type;
    }

    // 显示宝可梦信息的方法
    public String getInfo() {
        return name + " (" + type + ")";
    }

    // 进化宝可梦的方法
    // 接收新名字参数，更改名字并输出进化后的信息
    public void evolve(String newName) {
        this.name = newName; // 更改名字
        System.out.println("进化后: " + getInfo()); // 输出进化后的信息
    }
}
```


---

# 🔹 2. 为宝可梦类添加使用 if 语句、for 循环和数组的处理

## ✅ 扩展 Pokemon 类

请根据以下规格，在 `Pokemon` 类中添加 `learnMoves(String[] moves)` 方法。

### 新增方法

- `learnMoves(String[] moves)`  
  - 显示宝可梦可以学习的招式列表。  
  - 将数组 `moves` 中的每个招式名称按顺序输出。  
  - 如果数组为 `null` 或为空，则输出 `"没有可以学习的招式"`。

---

## 🖨 输出示例

### 输入值
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
String[] moves = {"Thunderbolt", "Quick Attack", "Iron Tail"};
p.learnMoves(moves);
```

### 输出值
```
Pikachu 可以学习的招式:
- Thunderbolt
- Quick Attack
- - Iron Tail
```

---

## ✅ 示例代码
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

    // 学习招式的方法。使用 if 语句、for 循环和数组进行处理
    public void learnMoves(String[] moves) {
        // 如果没有指定任何招式
        if (moves == null || moves.length == 0) {
            System.out.println("没有可以学习的招式");
            return;
        }

        // 如果有招式，逐个显示
        System.out.println(name + " 可以学习的招式:");
        for (String move : moves) {
            System.out.println("- " + move); // 显示每个招式
        }
    }
}
```


---


# 🔹 3. 从宝可梦类继承皮卡丘类

## ✅ 创建 Pikachu 类

- 请创建一个继承 `Pokemon` 类的 `Pikachu` 类，并在构造函数中将名字设为 `"Pikachu"`，属性设为 `"Electric"`。

---

## 🖨 输出示例

### 输入值
```java
Pikachu pika = new Pikachu();
System.out.println(pika.getInfo());
```

### 输出值
```
Pikachu (Electric)
```

---

## ✅ 示例代码
```java
public class Pikachu extends Pokemon {

    // Pikachu 专用构造函数。自动设置名字和属性
    public Pikachu() {
        setName("Pikachu");   // 设置名字为"Pikachu"
        setType("Electric");  // 设置属性为"Electric"
    }
}
```

---

# 🔹 4. 从皮卡丘类继承雷丘类

## ✅ 创建 Raichu 类

- 请创建一个继承 `Pikachu` 类的 `Raichu` 类，在构造函数中将名字覆盖为 `"Raichu"`。

---

## 🖨 输出示例

### 输入值
```java
Raichu r = new Raichu();
System.out.println(r.getInfo());
```

### 输出值
```
Raichu (Electric)
```

---

## ✅ 示例代码
```java
public class Raichu extends Pikachu {

    // Raichu 构造函数。继承自 Pikachu 的属性，同时修改名字
    public Raichu() {
        setName("Raichu"); // 设置名字为"Raichu"（属性仍为Electric）
    }
}
```


---

# 🔹 5. 从宝可梦类继承伊布类

## ✅ 创建 Eevee 类

- 请创建一个继承 `Pokemon` 类的 `Eevee` 类，在构造函数中将名字设为 `"Eevee"`，属性设为 `"Normal"`。

---

## 🖨 输出示例

### 输入值
```java
Eevee e = new Eevee();
System.out.println(e.getInfo());
```

### 输出值
```
Eevee (Normal)
```

---

## ✅ 示例代码
```java
public class Eevee extends Pokemon {

    // Eevee 构造函数，进行初始设置
    public Eevee() {
        setName("Eevee");     // 设置名字为"Eevee"
        setType("Normal");    // 设置属性为"Normal"
    }
}
```

---

# 🔹 6. 从宝可梦类继承杰尼龟类

## ✅ 创建 Squirtle 类

- 请创建一个继承 `Pokemon` 类的 `Squirtle` 类，在构造函数中将名字设为 `"Squirtle"`，属性设为 `"Water"`。

---

## 🖨 输出示例

### 输入值
```java
Squirtle s = new Squirtle();
System.out.println(s.getInfo());
```

### 输出值
```
Squirtle (Water)
```

---

## ✅ 示例代码
```java
public class Squirtle extends Pokemon {

    // Squirtle 构造函数，进行初始设置
    public Squirtle() {
        setName("Squirtle");  // 设置名字为"Squirtle"
        setType("Water");     // 设置属性为"Water"
    }
}
```

---

# 🔹 7. 重构宝可梦类并添加新功能

## ✅ 重构 Pokemon 类

请根据以下内容，向 Pokemon 类添加字段与方法。

### 添加字段

- `level`（类型: int）：宝可梦的等级（初始值为1）

### 添加方法

- `getLevel()` / `setLevel(int level)`
- `levelUp()`：将等级提升1，并输出例如 `"Pikachu的等级变成了6！"` 的信息

---

## 🖨 输出示例

### 输入值
```java
Pokemon p = new Pokemon();
p.setName("Pikachu");
p.setType("Electric");
p.setLevel(5);
p.levelUp();
System.out.println(p.getLevel());
```

### 输出值
```
Pikachu的等级变成了6！
6
```

---

## ✅ 示例代码
```java
public class Pokemon {
    private String name;
    private String type;
    private int level = 1; // 初始等级为1

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

    public int getLevel() {
        return level;
    }

    public void setLevel(int level) {
        this.level = level;
    }

    public void levelUp() {
        level += 1;
        System.out.println(name + "的等级变成了" + level + "！");
    }
}
```

---

# 🔹 8. 说明继承类在第7项重构后的影响

## ✅ 影响说明

### 要点

- 由于 `Pokemon` 类添加了 `level` 字段和 `levelUp()` 方法，所有子类（如 Pikachu、Raichu、Eevee、Squirtle 等）**自动具备等级管理功能**。
- 例如，可以对 `Raichu` 实例使用 `setLevel(10)` 或 `levelUp()`。
- 因此，**代码的重用性提高**，每个进化形态的宝可梦都能共享相同的成长逻辑。

### 示例：
```java
Raichu r = new Raichu();
r.setLevel(10);
r.levelUp(); // => Raichu的等级变成了11！
```

---

## ✅ 优势总结

- 可在基类统一管理等级功能
- 子类无需变更即可继承等级相关功能
- 添加方法时，影响范围最小化，设计更优
