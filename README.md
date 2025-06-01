# 📝 Pac-Man Game: Data Structures and Algorithms Report

## 📁 Project Structure Summary
The game consists of multiple classes managing gameplay (`Game`, `GamePanel`), rendering (`MainMenu`), entities (`Player`, `Ghost`, `Entity`), settings (`GameSettings`), logic (`Direction`), and state (`Board`).

---

## 🧱 1. **Data Structures Used**

| Class           | Data Structures                                                                 |
|-----------------|----------------------------------------------------------------------------------|
| `Entity`, `Player`, `Ghost` | Primitive fields (`int x, y, dx, dy`), reference to game board |
| `Board`         | 2D Array: `GameObject[][] board` – stores map layout                            |
| `Game`          | Object references to `Board`, `Player`, `Ghost[]`, score, level info            |
| `GamePanel`     | Swing components (`JPanel`, `Timer`), object instances, game loop control       |
| `Direction`     | Enum for fixed direction set                                                    |
| `GameSettings`  | Static fields (constants) for game tuning                                       |
| `MainMenu`      | GUI components (`JPanel`, `JButton`)                                            |

---

## 🧠 2. **Algorithms Implemented**

| Area                  | Description                                                                 | Class Involved               | Complexity |
|-----------------------|-----------------------------------------------------------------------------|------------------------------|------------|
| **Movement Logic**    | Calculates next position from direction; validates move                    | `Entity`, `Player`, `Ghost` | O(1)       |
| **Input Handling**    | Translates key presses to direction                                         | `GamePanel`, `Direction`     | O(1)       |
| **Game Loop**         | Uses `Timer` to run updates and repaint every tick                         | `GamePanel`                  | O(n) per tick (n = number of entities) |
| **Collision Detection** | Checks for wall or ghost collisions using tile values                   | `Player`, `Ghost`            | O(1)       |
| **Power-Up Handling** | Turns ghosts scared and changes their behavior                             | `Ghost`, `Player`, `Game`    | O(n)       |
| **State Management**  | Handles game start, reset, scoring, and level transitions                  | `Game`, `GamePanel`          | O(1)–O(n)  |

---

## ⏱️ 3. **Time Complexities**

| Task                                  | Time Complexity | Notes                                                       |
|---------------------------------------|------------------|-------------------------------------------------------------|
| Player/Ghost Movement                 | O(1)             | Based on direct access to 2D board array                    |
| Game Loop Update                      | O(n)             | Updates all active game objects per tick                    |
| Rendering (`paintComponent`)          | O(n)             | Dependent on number of drawable objects                     |
| Keyboard Input Processing             | O(1)             | Direct mapping to direction enum                            |
| Ghost Behavior Update (if scared)     | O(n)             | Iterate over all ghosts                                     |

---

## 🧩 4. **Design Highlights**

- **OOP Design**: Uses inheritance and polymorphism (`Entity` is extended by `Player` and `Ghost`).
- **Enum Use**: `Direction` enum offers readable, maintainable direction logic.
- **Modular Structure**: Settings (`GameSettings`), Rendering (`GamePanel`), Logic (`Game`, `Board`) are separated.
- **Efficient Access**: Board stored as `GameObject[][]` allows O(1) movement and collision logic.

---

## ✅ Conclusion

Our Pac-Man game demonstrates strong use of:
- Basic and efficient data structures like arrays and enums.
- Classic real-time game loop and movement algorithms.
- Clean separation of concerns through object-oriented design.

This project is a solid representation of applying **Data Structures and Algorithms** to a real-world interactive system.
