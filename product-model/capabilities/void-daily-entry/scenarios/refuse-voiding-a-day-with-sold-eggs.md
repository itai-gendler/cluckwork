---
kind: validation
routes:
  web: Web
steps:
- text: The Manager voids a day one of whose lots has already sold eggs
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: farm-web::farm::history
- text: The Product refuses the void and names the grade; nothing changes
  kind: condition
  actor: manager
  entities:
  - entity: egg-lot
    effect: reads
    facts:
    - Produced
    - Available
  - entity: daily-entry
    effect: reads
    facts: []
  contexts:
    web:
      place: farm-web::farm::history
---

# Refuse voiding a day whose eggs were sold

## Trigger

Eggs from the day have already left the farm on a sale.

## Outcome

The day stays official; the sale must be voided first.

## Edge cases

- A day of an archived flock cannot be voided until the flock is reactivated.
