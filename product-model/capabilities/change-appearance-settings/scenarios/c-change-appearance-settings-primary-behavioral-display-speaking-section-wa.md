---
{
  "kind": "primary",
  "routes": {
    "route": "WA Behavioral display/speaking section"
  },
  "steps": [
    {
      "text": "Change appearance settings request: Behavioral display/speaking section.",
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
          "place": "web::authenticated::consultation-settings"
        }
      }
    },
    {
      "text": "Behavioral display/speaking settings persist without prescribing visual style.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "changes",
          "facts": [
            "Display settings"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-settings"
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

# Change appearance settings — Behavioral display/speaking section — WA

## Trigger

Change appearance settings request: Behavioral display/speaking section.

## Outcome

Behavioral display/speaking settings persist without prescribing visual style.
