---
{
  "kind": "primary",
  "routes": {
    "route": "AA Motion"
  },
  "steps": [
    {
      "text": "Revoke support request: selected item.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Matching account/cookie-owned official support is removed.",
      "kind": "product",
      "actor": "user",
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
          "place": "antragsgruen-api::authenticated"
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

# Revoke support — Motion — AA

## Trigger

Revoke support request: Motion.

## Outcome

Matching account/cookie-owned official support is removed.
