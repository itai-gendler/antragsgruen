---
{
  "kind": "validation",
  "routes": {
    "route": "WP Invalid confirmation"
  },
  "steps": [
    {
      "text": "Confirm email request: Invalid confirmation.",
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
          "place": "web::public::email-confirmation"
        }
      }
    },
    {
      "text": "Code/captcha fails or the pending target cannot be resolved. This attempt does not complete the requested operation.",
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
          "place": "web::public::email-confirmation"
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

# Confirm email — Invalid confirmation — WP

## Trigger

Confirm email request: Invalid confirmation.

## Outcome

Code/captcha fails or the pending target cannot be resolved. This attempt does not complete the requested operation.
