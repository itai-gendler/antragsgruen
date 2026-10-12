---
{
  "kind": "validation",
  "routes": {
    "route": "WP Invalid recovery"
  },
  "steps": [
    {
      "text": "Recover password request: Invalid recovery.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-recovery"
        }
      }
    },
    {
      "text": "Target/code is invalid or the new password fails length/repetition validation. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-recovery"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/LoginUsernamePasswordForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/UserController.php"
    }
  ]
}
---

# Recover password — Invalid recovery — WP

## Trigger

Recover password request: Invalid recovery.

## Outcome

Target/code is invalid or the new password fails length/repetition validation. This attempt does not complete the requested operation.
