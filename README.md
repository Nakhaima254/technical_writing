# Syntax and Structure Guide  

## Overview  
This guide provides an overview of the syntax and structural conventions used in this project. Following consistent syntax and structure ensures readability, maintainability, and collaboration efficiency.  

---  

## File Naming Conventions  
- Use **kebab-case** for file and folder names (e.g., `data-processor.js`, `styles.css`).  
- Prefix test files with the name of the tested module (e.g., `user-service.test.js`).  
- Configuration files should be named in lowercase (e.g., `config.json`, `.eslintrc`).  

---  

## Code Structure  

### General Formatting  
- Use **2 spaces** for indentation (no tabs).  
- Keep line lengths under **80 characters** for readability.  
- Always end files with a **newline**.  

### JavaScript/TypeScript  
```javascript  
// Use strict mode  
"use strict";  

// Use camelCase for variables and functions  
const userName = "JohnDoe";  

function calculateTotalPrice(items) {  
  return items.reduce((sum, item) => sum + item.price, 0);  
}  

// Use PascalCase for classes  
class UserAccount {  
  constructor(name) {  
    this.name = name;  
  }  
}  

// Use UPPER_SNAKE_CASE for constants  
const MAX_RETRIES = 3;  
```  

### Python  
```python  
# Use snake_case for variables and functions  
user_name = "JohnDoe"  

def calculate_total_price(items):  
    return sum(item["price"] for item in items)  

# Use PascalCase for classes  
class UserAccount:  
    def __init__(self, name):  
        self.name = name  

# Use UPPER_SNAKE_CASE for constants  
MAX_RETRIES = 3  
```  

### HTML  
```html  
<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8">  
  <title>Page Title</title>  
  <link rel="stylesheet" href="styles.css">  
</head>  
<body>  
  <main>  
    <h1>Hello, World!</h1>  
  </main>  
</body>  
</html>  
```  

### CSS/SCSS  
```css  
/* Use kebab-case for class names */  
.user-card {  
  padding: 1rem;  
  border: 1px solid #ddd;  
}  

/* Nesting in SCSS */  
.container {  
  max-width: 1200px;  

  .header {  
    font-size: 2rem;  
  }  
}  
```  

---  

## Comments & Documentation  
- Use **JSDoc** for JavaScript/TypeScript functions:  
  ```javascript  
  /**  
   * Calculates the sum of two numbers.  
   * @param {number} a - First number.  
   * @param {number} b - Second number.  
   * @returns {number} Sum of a and b.  
   */  
  function add(a, b) {  
    return a + b;  
  }  
  ```  
- Use **docstrings** in Python:  
  ```python  
  def add(a, b):  
      """  
      Calculates the sum of two numbers.  
      Args:  
          a (int): First number.  
          b (int): Second number.  
      Returns:  
          int: Sum of a and b.  
      """  
      return a + b  
  ```  
- For inline comments, explain **why**, not **what**:  
  ```javascript  
  // Cache the result to avoid redundant API calls  
  const cachedData = fetchData();  
  ```  

---  

## Branching & Loops  
- Always use **braces** for blocks, even if single-line:  
  ```javascript  
  // Good  
  if (condition) {  
    doSomething();  
  }  

  // Avoid  
  if (condition) doSomething();  
  ```  
- Use **early returns** to reduce nesting:  
  ```javascript  
  function processUser(user) {  
    if (!user) return null;  
    if (!user.isActive) return "Inactive user";  

    // Main logic  
    return `Welcome, ${user.name}`;  
  }  
  ```  

---  

## Import/Export Statements  
- Group imports by type (external → internal):  
  ```javascript  
  // External dependencies  
  import React from "react";  
  import axios from "axios";  

  // Internal modules  
  import { UserService } from "./services/user-service";  
  ```  
- Use **named exports** for utilities and **default exports** for components:  
  ```javascript  
  // utils/math.js  
  export const add = (a, b) => a + b;  

  // components/Button.js  
  const Button = () => <button>Click Me</button>;  
  export default Button;  
  ```  

---  

## Best Practices  
✅ **Consistency** – Follow the same style across the project.  
✅ **Readability** – Write code as if someone else will maintain it.  
✅ **Modularity** – Break code into small, reusable functions/components.  
🚫 **Avoid** – Deep nesting, overly complex logic, and magic numbers.  

---  

## Linting & Formatting  
This project uses:  
- **ESLint** (JavaScript/TypeScript)  
- **Prettier** (Code formatting)  
- **Black** (Python formatting)  

Run linting before committing:  
```sh  
npm run lint  # For JavaScript/TypeScript  
black .       # For Python  
```  
