[![Made with C++](https://img.shields.io/badge/Made%20with-C++-blue.svg)](https://isocpp.org/)
[![ncurses](https://img.shields.io/badge/Uses-ncurses-green.svg)](https://invisible-island.net/ncurses/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform: Terminal](https://img.shields.io/badge/Platform-Terminal-lightgrey.svg)]()

# Pacman Clone 🎮
<p align="center">
  <img src="https://raw.githubusercontent.com/bobblet11/Pacman-game-cpp/master/playthrough_800px.gif" alt="Gameplay" width="1920">
</p>

A **Pacman clone written in C++** that runs entirely inside the terminal using **ncurses** and **termios**.  
Built as a fun project to explore terminal graphics, dynamic memory management, and file I/O.

---

## 📦 Installation & Quickstart

## 🔧 Dependencies

This project requires the **ncurses** development library to compile and run.

### Linux Installation

On **Ubuntu / Debian**:
```bash
sudo apt update
sudo apt install libncurses5-dev libncursesw5-dev
```

On **Fedora / RHEL / CentOS**:
```bash
sudo dnf install ncurses-devel
# or, on older systems:
sudo yum install ncurses-devel
```

### Build & Run
```bash
# Clone the repository
git clone https://github.com/bobblet11/Pacman-game-cpp.git
cd Pacman-game-cpp

# Compile
make

# Run (fullscreen recommended)
./pacman
```

---

## 🕹️ Showcase
![Model](https://raw.githubusercontent.com/bobblet11/Pacman-game-cpp/master/pacmangit2.png)
![Model](https://raw.githubusercontent.com/bobblet11/Pacman-game-cpp/master/pacmangit4.png)
![Model](https://raw.githubusercontent.com/bobblet11/Pacman-game-cpp/master/pacmangit3.png)
![Model](https://raw.githubusercontent.com/bobblet11/Pacman-game-cpp/master/pacmangit6.png)
- Navigate the **main menu** with arrow keys.  
- Enter a **username** to track high scores.  
- Play the game: eat all pills, avoid ghosts, and use super pills to turn the tables.  
- View **high scores** in the menu or after each playthrough.  

---

## ⚙️ Game Rules

- **Objective**: Form an expression equal to 24 using the four drawn cards.  
- **Gameplay**:  
  - Eat all pills on the map to win.  
  - Colliding with a ghost ends the game.  
  - Super pills make ghosts frightened and edible (worth 500 pts).  

---

## 👾 Ghost AI

Each ghost has a distinct randomized playstyle:
- **Red**: Aggressive, high chase accuracy.  
- **Purple**: Chases with lower probability.  
- **Cyan & Pink**: Ineffective chasers, scatter often, random moves.  

---

## 🛠️ Implementation Notes

- **Randomization**: Ghost AI uses probability‑based movement.  
- **Dynamic Memory**:  
  - Vector of pointers to dynamically allocated `GameObject` instances.  
  - Dynamic arrays for sprite data and animations.  
- **File I/O**:  
  - Text files for sprites, maps, and high scores.  
  - High scores saved per username (overwritten if beaten).  

---

## 📂 Project Structure

| File | Purpose |
|------|---------|
| **main.cpp** | Central game loop, memory allocation/deallocation |
| **Screen.cpp / Screen.h** | Rendering logic |
| **PlayableMap.cpp / .h / .txt** | Map loading & collision detection |
| **Pill.cpp / Pill.h / Pills.txt** | Pill objects & sprites |
| **Ghosts.cpp / Ghosts.h / GhostSprites.txt** | Ghost objects & sprites |
| **Character.cpp / .h / CharacterSprites.txt** | Player (Pacman) logic & sprites |
| **GameObject.cpp / .h** | Base template for all interactive objects |
| **Highscores.cpp / .h / highscores.txt** | High score persistence |
| **Menu / Item / Functions** | Menu system, input handling |

---

## 📖 Class Hierarchy

```
GameObject
   ├── Ghost
   ├── Pill
   └── Character
```

Other supporting classes: `Screen`, `Menu`, `Item`, `PlayableMap`.

---

## 📝 Documentation

- **Sprites & Maps**: Loaded from `.txt` files for easy customization.  
- **High Scores**: Stored in `highscores.txt`, tied to usernames.  
- **Dynamic Memory**: All objects allocated/deallocated at runtime.  

                          <CLASSES>
                       
        Screen    Menu    Item    PlayableMap      GameObject
                                                       |
                                                 :-----:----------:
                                                 v     v          v    
                                             Ghost    Pill    Character

---

## 🚀 Future Improvements
- Smarter ghost AI (pathfinding).  
- Multiple maps and difficulty levels.  
- Sound effects using terminal beeps or external libraries.  

---










