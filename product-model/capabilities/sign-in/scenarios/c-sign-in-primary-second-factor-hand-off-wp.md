---
{
  "kind": "primary",
  "routes": {
    "route": "WP Second-factor hand-off"
  },
  "steps": [
    {
      "text": "Sign in request: Second-factor hand-off.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      }
    },
    {
      "text": "Credential verification retains the pending Account and factor challenge, then carries the actor to second-factor verification.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
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
          "place": "web::public::sign-in"
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

# Sign in — Second-factor hand-off — WP

## Trigger

Sign in request: Second-factor hand-off.

## Outcome

Credential verification retains the pending Account and factor challenge, then carries the actor to second-factor verification.
