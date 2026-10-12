---
{
  "kind": "validation",
  "routes": {
    "route": "WA Deactivation refused"
  },
  "steps": [
    {
      "text": "Delete account request: Deactivation refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "Administrative self-deletion or an account restriction stops deactivation. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "membership",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
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

# Delete account — Deactivation refused — WA

## Trigger

Delete account request: Deactivation refused.

## Outcome

Administrative self-deletion or an account restriction stops deactivation. This attempt does not complete the requested operation.
