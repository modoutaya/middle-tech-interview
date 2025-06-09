# Count Primes

Given an integer `n`, return _the number of prime numbers that are strictly less than_ `n`.


### **Example 1:**
    Input: n = 10
    Output: 4
    Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
    
### **Example 2:**
    Input: n = 0
    Output: 0
    
### **Example 3:**
    Input: n = 1
    Output: 0
    
Code Editor: https://playcode.io/typescript

---

# Team Management API (PHP – Clean Archi)

## 🎯 Objective

Build a minimal backend service in **PHP** to manage **teams and their members**, following **Clean Architecture** principles.  
This exercise is designed to evaluate your ability to:
- Model a simple business domain
- Apply clean separation of concerns
- Write clear, testable, and maintainable PHP code

---

## ⚙️ Technical Requirements

- **Language**: PHP ≥ 8.0
- **Architecture**: Clean Architecture  
- **Storage**: In-memory only (arrays or singleton objects)
- **Frameworks**: None (no Symfony, Laravel, etc.)
- **Testing**: Optional (bonus points for testing one use case)

---

## 🧱 Features to Implement

### 1. Create a Team  
**POST** `/teams`  
**Request:**
```json
{
  "name": "Team Rocket"
}

Response:
{
  "id": "team_abc123",
  "name": "Team Rocket"
}
```

### 2. Add a Member to a Team
**POST** `/teams/{teamId}/members`  
**Request:**
```json
{
  "memberId": "user-123",
  "email": "jessie@example.com"
}

Response:
{
  "memberId": "user-123",
  "email": "jessie@example.com"
}
```


### 3. Add a Member to a Team
**GET** `/teams/{teamId}/members`  
Response:
```json
[
  {
    "memberId": "user-123",
    "email": "jessie@example.com"
  },
  {
    "memberId": "user-456",
    "email": "james@example.com"
  }
]
```

## 📏 Business Rules

- A team **must have a name** (non-empty).
- A team ID is **auto-generated** (e.g., using `uniqid()` or UUID).
- A team can have multiple members.
- A member must have:
  - a **memberId** (string)
  - a **valid email address** (basic format check)
- A given `memberId` **cannot be added more than once** to the same team.
- The same `memberId` **can exist in multiple teams**.
- The same email can be reused in different teams.
- If the team does not exist (when adding or listing members), the system must return a **404 – Team Not Found** error.
- No update or delete operation is required for teams or members.

Code Editor: https://replit.com
