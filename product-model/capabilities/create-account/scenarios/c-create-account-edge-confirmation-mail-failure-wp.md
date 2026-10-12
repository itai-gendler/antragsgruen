---
{
  "kind": "edge",
  "routes": {
    "route": "WP Confirmation-mail failure"
  },
  "steps": [
    {
      "text": "Create account request: Confirmation-mail failure.",
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
      "text": "Persistence precedes confirmation mail; failure is reported without a delivery promise.",
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
          "to": "Unconfirmed"
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

# Create account — Confirmation-mail failure — WP

## Trigger

Create account request: Confirmation-mail failure.

## Outcome

Persistence precedes confirmation mail; failure is reported without a delivery promise.
