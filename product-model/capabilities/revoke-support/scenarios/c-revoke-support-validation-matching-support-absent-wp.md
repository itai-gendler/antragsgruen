---
{
  "kind": "validation",
  "routes": {
    "route": "WP Matching support absent"
  },
  "steps": [
    {
      "text": "Revoke support request: Matching support absent.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
        }
      }
    },
    {
      "text": "No matching support belongs to this request's identity. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Permissions.php"
    }
  ]
}
---

# Revoke support — Matching support absent — WP

## Trigger

Revoke support request: Matching support absent.

## Outcome

No matching support belongs to this request's identity. This attempt does not complete the requested operation.
