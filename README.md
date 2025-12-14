# 🐍 Advanced Snake Game (C# Windows Forms)

A modern, feature-rich implementation of the classic Snake game developed in C# using Windows Forms and GDI+ for custom rendering. This project focuses on advanced game mechanics, a dynamic speed system, and a customizable, themed user interface.

## ✨ Key Features

### 1. Dynamic Game Speed System
The game features a unique three-layer speed calculation, ensuring the difficulty scales dynamically while respecting user settings:
* **Base Speed:** Set by the user via the `Speed Selector` (Very Slow, Normal, Extreme).
* **Leveling Speed:** The game gets progressively faster by reducing the interval by **10ms every 50 score points**.
* **Temporary Effects:** Speed is temporarily modified by special food items (Fast or Slow).

### 2. Advanced Special Food System (Risk & Reward)
In addition to standard food, special food items have a 20% chance to spawn for **7 seconds**, introducing strategic gameplay:
| Food Type | Effect | Risk / Reward |
| :--- | :--- | :--- |
| **Bonus** (Yellow) | Grants +50 score. | High reward, but disappears fast. |
| **Fast** (Orange) | Temporarily increases speed (-30ms interval). | Helps cover distance faster. |
| **Slow** (Blue) | Temporarily decreases speed (+30ms interval). | Provides a brief moment to react. |
| **Bomb** (Purple) | **Removes 3 segments** from the snake's tail. | High risk! If the snake is too short, it's Game Over. |

### 3. Customizable UI/UX & Theming
The UI is styled using custom GDI+ rendering (GraphicsPath and custom Paint events) to achieve a modern aesthetic:
* **Theming:** Switch between three predefined color schemes: **Neon (Default), Dark, and Light**.
* **Custom Colors:** Use the **Settings** menu to pick custom colors for the **Snake Head/Body**, **Game Board**, and **Normal Food**.
* **Responsive Design:** The game grid scales automatically to fit the `pnlGame` dimensions, ensuring perfect rendering on window resize.

### 4. Accessibility
* Supports both **Arrow Keys** and **WASD** input for movement.
* Toggle sound effects on/off via the Settings menu.

## 🕹️ How to Play

### Controls
| Key / Control | Action |
| :--- | :--- |
| **Arrow Keys / WASD** | Change Snake Direction |
| **Space Bar** | Pause and Resume Game |
| **R Key** | Restart Game |
| **Settings Button** | Open Configuration Menu (Auto-pauses game) |

### Game Rules
* Eat **Normal Food** for 10 points and growth.
* Eat **Special Food** quickly before it disappears after 7 seconds.
* Avoid running into the walls or your own tail.
* Avoid the **Bomb** if your snake is short!

## 🛠️ Installation and Setup

This project requires **Visual Studio** and the **.NET Framework (or .NET Core/5+ installed)** to build and run.

1.  **Clone the Repository:**
    ```bash
    git clone [YOUR_REPO_URL]
    cd snakeassignment
    ```
2.  **Open in Visual Studio:**
    * Open the `snakeassignment.sln` file in Visual Studio.
3.  **Build and Run:**
    * Set the project as the startup project.
    * Press `F5` or click **Start** to build and run the game.

## 🧑‍💻 Design Highlights (For Developers)

* **Polymorphism:** The food system is implemented using an abstract base class (`FoodBase`) and derived classes (`NormalFood`, `SpecialFood`), allowing for clean expansion of new food types.
* **Separation of Concerns:** The UI styling logic is separated into utility methods (`SetupButton`, `SetupRadioButton`, etc.), improving maintainability.
* **Custom Rendering:** Advanced use of `System.Drawing.Drawing2D.GraphicsPath` in `OnPaint` and custom control paint handlers to render complex shapes (rounded boxes, pill buttons) that are not natively supported by standard WinForms controls.

## ✍️ Author

This game was developed by **Noor fatima**.

## ⚖️ License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
