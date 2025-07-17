# Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

### **Example 1:**
    Input: strs = ["flower","flow","flight"]
    Output: "fl"
    
### **Example 2:**
    Input: strs = ["dog","racecar","car"]
    Output: ""
    Explanation: There is no common prefix among the input strings.

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
