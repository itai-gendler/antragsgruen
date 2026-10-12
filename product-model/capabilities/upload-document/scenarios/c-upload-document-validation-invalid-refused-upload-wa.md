---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused upload"
  },
  "steps": [
    {
      "text": "Upload document request: Invalid/refused upload.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "document",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
        }
      }
    },
    {
      "text": "Upload/parent validation fails. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "document",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
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

# Upload document — Invalid/refused upload — WA

## Trigger

Upload document request: Invalid/refused upload.

## Outcome

Upload/parent validation fails. This attempt does not complete the requested operation.
