---
{
  "kind": "validation",
  "routes": {
    "route": "WA Change refused"
  },
  "steps": [
    {
      "text": "Change site access settings request: Change refused.",
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
      "text": "The actual site operation check stops the change. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Change site access settings — Change refused — WA

## Trigger

Change site access settings request: Change refused.

## Outcome

The actual site operation check stops the change. This attempt does not complete the requested operation.
