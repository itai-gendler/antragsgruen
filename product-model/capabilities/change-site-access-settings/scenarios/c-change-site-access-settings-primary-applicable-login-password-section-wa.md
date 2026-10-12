---
{
  "kind": "primary",
  "routes": {
    "route": "WA Applicable login/password section"
  },
  "steps": [
    {
      "text": "Change site access settings request: Applicable login/password section.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
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
      "text": "Applicable site login/password settings persist.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "changes",
          "facts": [
            "Access settings"
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

# Change site access settings — Applicable login/password section — WA

## Trigger

Change site access settings request: Applicable login/password section.

## Outcome

Applicable site login/password settings persist.
