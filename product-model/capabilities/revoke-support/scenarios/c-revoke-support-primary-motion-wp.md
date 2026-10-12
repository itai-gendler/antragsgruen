---
{
  "kind": "primary",
  "routes": {
    "route": "WP Motion"
  },
  "steps": [
    {
      "text": "Revoke support request: Motion.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
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

# Revoke support — Motion — WP

## Trigger

Revoke support request: Motion.

## Outcome

Matching account/cookie-owned official support is removed.
