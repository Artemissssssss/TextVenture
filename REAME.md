<div align="center">
    
# ︵‿︵‿୨TextVenture ୧‿︵‿︵

---

Time to take an adventure through text.

</div>

## 📌 Overview

TextVenture is a console-based Java program guiding the player through branching narrative paths.  
It uses menus, choices, and story routes to create an immersive text-based adventure while demonstrating **Object-Oriented Programming (OOP) principles** through modular classes, dynamic flow, and reusable components.

---

## 🔒 1️⃣ Encapsulation

**💡 What it is:**  
Encapsulation is about **safeguarding data** inside a class and controlling access through methods.

**🎮 How it’s used:**

- `GameState` keeps player stats (`respect`, `fear`, `bravery`) **private**.
- Methods like `addRespect()`, `addFear()`, `addBravery()` **safely update stats**, protecting game integrity.

**⚡ Example:**

```java
public void addRespect(int v) {
    respect += v;
}
```

---

## 🌳 2️⃣ Inheritance

**💡 What it is:**
Inheritance allows a class to **reuse and extend** features of another class.

**🎮 How it’s used:**

- `Path` is an **abstract parent class** with shared properties (`playerName`, `Scanner input`) and helper methods.
- `Path1`, `Path2`, `Path3` **extend `Path`**, inheriting functionality while implementing story-specific logic.

**⚡ Example:**

```java
class Path1 extends Path { ... }
class Path2 extends Path { ... }
```

---

## 🔄 3️⃣ Polymorphism

**💡 What it is:**
Polymorphism lets **different objects behave through a common interface**.

**🎮 How it’s used:**

- Each path (`Path1`, `Path2`, `Path3`) **overrides `playPath()`**.
- Calling `playPath()` on a `Path` reference executes the correct subclass logic dynamically.

**⚡ Example:**

```java
Path path = new Path1(playerName, input);
path.playPath(); // Executes Path1's unique story logic
```

---

## 🕵️‍♂️ 4️⃣ Abstraction

**💡 What it is:**
Abstraction hides complex details and shows only **essential functionality**.

**🎮 How it’s used:**

- `Path` is **abstract** with method `playPath()`.
- Subclasses implement story-specific logic, keeping the game engine clean.

**⚡ Example:**

```java
abstract class Path {
    public abstract void playPath();
}
```

---

## 🏗️ Game Structure & Class Roles

### 🎯 Main Classes

- **`Interactive_Story_App`** → Main entry point; shows menus, handles user input, starts the game.
- **`DelayPrinter`** → Prints text slowly for immersion.
- **`LoadingBar`** → Displays a loading animation before the story begins.
- **`Path`** (abstract) → Base class for story paths; contains shared properties and helper methods.
- **`Path1`, `Path2`, `Path3`** → Subclasses; override `playPath()` with unique story logic.
- **`InteractiveStoryGame`** → Handles game state and engine:

  - `GameState` → Tracks player stats
  - `GameStateHolder` → Stores current game state
  - `GameEngine` → Runs the story

- **`ReturnToMenuException`** → Custom exception for returning to the main menu.

---

### 🖇️ Class Relationships

```
Interactive_Story_App
│
├── DelayPrinter
├── LoadingBar
├── Path (abstract)
│    ├── Path1
│    ├── Path2
│    └── Path3
└── InteractiveStoryGame
     ├── GameState
     ├── GameStateHolder
     └── GameEngine

ReturnToMenuException – used by Path & GameEngine for control flow
```

---

## ▶️ How to Run the Program

**Requirements:** Java JDK (8+) and a terminal/command prompt.

1️⃣ **Compile the program:**

```bash
javac Interactive_Story_App.java
```

2️⃣ **Run the game:**

```bash
java Interactive_Story_App
```

3️⃣ **Play:**

- Type the number of your choice and press **ENTER**
- Type **0** to return to the main menu anytime
- Explore different paths and enjoy the story!

💡 **Tip:** The game uses **slow printing** and **mini-events** for suspense — enjoy the journey!

---

## 🖥️ Sample Output

> ![Sample1](Samples/p1.png) > ![Sample1](Samples/p2.png)

---

## 👥 Authors

- **De Gracia, Niela Alena**
  BS Computer Science student at Batangas State University – The National Engineering University.
  GitHub: [@NielaAlena](https://github.com/nielaalena)

- **Labrador, Matthew Louis**
  Loves creating things and improving skills along the way.
  GitHub: [@MatthewLouis](https://github.com/Artemissssssss)

- **Magbuhat, Julian Carlo**
  CS student at Batangas State University; interested in gaming, videography, and coding.
  GitHub: [@JulianCarlo](https://github.com/juliancarlomagbuhat)

---

## 🙏 Acknowledgements

- **Almighty God** – for knowledge, wisdom, and courage
- **Sir Emman** – for guidance and encouragement
- **Family & Friends** – for support, patience, and motivation

---

## 🚀 Future Enhancements

- **Expanded Storyline:** More branches, endings, and character interactions
- **Additional Stories:** Allow players to choose from multiple adventures
- **Graphical & Multimedia Elements:** GUI, music, sound effects, images
- **Save & Load Feature:** Continue progress and explore different outcomes
