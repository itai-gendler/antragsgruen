---
{
  "kind": "edge",
  "routes": {
    "route": "WA Strict posted-key comparison leaves unmatched input unchanged"
  },
  "steps": [
    {
      "text": "Delete consultation request: Strict posted-key comparison leaves unmatched input unchanged.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
        }
      }
    },
    {
      "text": "A posted key not strictly equal to the stored key leaves the unmatched consultation unchanged.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/IndexController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Delete consultation — Strict posted-key comparison leaves unmatched input unchanged — WA

## Trigger

Delete consultation request: Strict posted-key comparison leaves unmatched input unchanged.

## Outcome

A posted key not strictly equal to the stored key leaves the unmatched consultation unchanged.
