# Ellen's Alien Game

## Instructions for the Problem

[Ellen's Alien Game Exercise](https://exercism.org/tracks/cpp/exercises/ellens-alien-game/edit)


# Instructions

Ellen is creating a game where players fight aliens. She has just learned about **Object-Oriented Programming (OOP)** and wants to use **classes** to structure her code.

To assist Ellen, you need to **program the aliens** that the player will fight.

## Alien Class Requirements

1. **Define an `Alien` class** with a constructor that accepts two `int` parameters (`x` and `y`), initializing them as `x_coordinate` and `y_coordinate` member variables.
2. Each alien should start with **a health level of `3`**, stored in a private `health` member variable.
3. Provide a **public method `get_health()`** that returns the current health.

### Example Usage:

```cpp
Alien alien{2, 0};
alien.x_coordinate;  // => 2
alien.y_coordinate;  // => 0
alien.get_health();  // => 3
```

---

## Adding Functionality

### 1. Implement the `hit()` Method
- This method **decrements** the alien's health by `1` (but **not below `0`**).
- The function should return `true`.
- Later, **shields** may be introduced that prevent health reduction.

#### Example:

```cpp
Alien alien {0, 0};
alien.get_health(); // => 3  (Initial health value)

alien.hit(); 
alien.get_health(); // => 2
```

---

### 2. Implement `is_alive()` Method
- This method returns a **boolean** indicating if the alien is alive (`true` if health > 0, otherwise `false`).

#### Example:

```cpp
alien.get_health(); // => 1
alien.is_alive();   // => true

alien.hit();
alien.get_health(); // => 0
alien.is_alive();   // => false
```

---

### 3. Implement the `teleport()` Method
- This method takes **`x_new`** and **`y_new`** values and **updates the alien's coordinates**.
- For now, the function should return `true`.
- Later, **teleport-blocking bombs** may prevent movement.

#### Example:

```cpp
alien.teleport(5, -4);
alien.x_coordinate; // => 5
alien.y_coordinate; // => -4
```

---

### 4. Implement `collision_detection()`
- This method takes **another `Alien` object** as an argument.
- It returns `true` **if both aliens occupy the same coordinates**; otherwise, it returns `false`.

#### Example:

```cpp
Alien lrrr {3, 6};
Alien ndnd {-2, 12};

lrrr.collision_detection(ndnd); // => false

ndnd.teleport(3, 6);
ndnd.collision_detection(lrrr); // => true
```

