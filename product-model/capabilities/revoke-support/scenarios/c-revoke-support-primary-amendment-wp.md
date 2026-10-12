---
{
  "kind": "primary",
  "routes": {
    "route": "WP Amendment"
  },
  "steps": [
    {
      "text": "Revoke support request: Amendment.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
        }
      }
    },
    {
      "text": "Matching account/cookie-owned official support is removed.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "supporter",
          "effect": "removes"
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
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

# Revoke support — Amendment — WP

## Trigger

Revoke support request: Amendment.

## Outcome

Matching account/cookie-owned official support is removed.
