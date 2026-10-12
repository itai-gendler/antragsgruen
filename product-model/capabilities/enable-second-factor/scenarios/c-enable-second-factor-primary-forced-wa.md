---
{
  "kind": "primary",
  "routes": {
    "route": "WA Forced"
  },
  "steps": [
    {
      "text": "Enable second factor request: Forced.",
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
          "place": "web::authenticated::sign-in"
        }
      }
    },
    {
      "text": "Enrollment proof saves factor configuration; required enrollment completes pending authentication.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Second-factor configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
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

# Enable second factor — Forced — WA

## Trigger

Enable second factor request: Forced.

## Outcome

Enrollment proof saves factor configuration; required enrollment completes pending authentication.
