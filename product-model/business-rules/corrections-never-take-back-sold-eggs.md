---
appliesTo:
- type: capability
  id: adjust-daily-entry
- type: capability
  id: void-daily-entry
- type: entity
  id: egg-lot
  facts:
  - Produced
  - Available
references:
- kind: code
  role: implementation
  target: src/Cluckwork.Domain/Modules/EggOperations/Eggs/EggLot.cs#AdjustProduction
---

# A correction never sets a lot below what it already sold

Adjusting a day can grow, shrink, add or empty its lots but never below the eggs a lot has sold, allocated or written off; voiding a day is refused if any of its eggs were sold.
