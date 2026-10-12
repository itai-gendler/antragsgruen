---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/duplicate address"
  },
  "steps": [
    {
      "text": "Create page request: Invalid/duplicate address.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page-administration"
        }
      }
    },
    {
      "text": "Address is invalid or duplicate. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page-administration"
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

# Create page — Invalid/duplicate address — WA

## Trigger

Create page request: Invalid/duplicate address.

## Outcome

Address is invalid or duplicate. This attempt does not complete the requested operation.
