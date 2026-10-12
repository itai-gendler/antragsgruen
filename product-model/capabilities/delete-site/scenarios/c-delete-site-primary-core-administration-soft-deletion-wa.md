---
{
  "kind": "primary",
  "routes": {
    "route": "WA Core administration soft deletion"
  },
  "steps": [
    {
      "text": "Delete site request: Core administration soft deletion.",
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
          "place": "web::authenticated::consultation-administration"
        }
      }
    },
    {
      "text": "Core administrative entry marks the site deleted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "changes",
          "facts": [
            "Deleted"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-administration"
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

# Delete site — Core administration soft deletion — WA

## Trigger

Delete site request: Core administration soft deletion.

## Outcome

Core administrative entry marks the site deleted.
