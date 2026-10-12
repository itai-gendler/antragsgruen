---
{
  "kind": "primary",
  "routes": {
    "route": "WP Immediately confirmed"
  },
  "steps": [
    {
      "text": "Create account request: Immediately confirmed.",
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
          "place": "web::public::sign-in"
        }
      }
    },
    {
      "text": "The new local account is saved Confirmed. With no password-change or second-factor continuation required, the Web session is established and the person returns to the requested destination.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Name",
            "Email",
            "Organization",
            "Authentication identity",
            "Email confirmation",
            "Password configuration",
            "Second-factor configuration",
            "Account restrictions",
            "Vote weights",
            "Pending email change",
            "Preferred language"
          ],
          "to": "Confirmed"
        },
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Session context"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionLogin"
    }
  ]
}
---

# Create account — Immediately confirmed — WP

## Trigger

Create account request: Immediately confirmed.

## Outcome

The new local account is saved Confirmed. With no password-change or second-factor continuation required, the Web session is established and the person returns to the requested destination.
