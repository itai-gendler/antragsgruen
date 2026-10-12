---
{
  "kind": "primary",
  "routes": {
    "route": "WA Email-confirmation hand-off"
  },
  "steps": [
    {
      "text": "Sign in request: Email-confirmation hand-off.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
        }
      }
    },
    {
      "text": "Credential verification retains the pending Account and carries the actor to email confirmation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Pending authentication"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Authentication identity",
            "Email confirmation",
            "Password configuration",
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

# Sign in — Email-confirmation hand-off — WA

## Trigger

Sign in request: Email-confirmation hand-off.

## Outcome

Credential verification retains the pending Account and carries the actor to email confirmation.
