# Thoughtful Automation - Package Sorting Logic

This repository contains a simple Python function to classify packages in a robotic automation factory into appropriate stacks: `STANDARD`, `SPECIAL`, or `REJECTED`.

## 📦 Classification Rules

- **Bulky**:
  - Volume ≥ 1,000,000 cm³ OR
  - Any dimension ≥ 150 cm
- **Heavy**:
  - Mass ≥ 20 kg

## 🧠 Stack Logic

| Bulky | Heavy | Stack     |
|-------|--------|-----------|
| No    | No     | STANDARD  |
| Yes   | No     | SPECIAL   |
| No    | Yes    | SPECIAL   |
| Yes   | Yes    | REJECTED  |

## 🚀 Usage

```python
from sort import sort

print(sort(100, 100, 100, 10))  # STANDARD
print(sort(160, 40, 40, 10))    # SPECIAL
print(sort(100, 100, 100, 25))  # SPECIAL
print(sort(160, 160, 160, 25))  # REJECTED
