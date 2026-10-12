---
{
  "kind": "primary",
  "routes": {
    "route": "WP Later confirmation"
  },
  "steps": [
    {
      "text": "Confirm email request: Later confirmation.",
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
      "text": "The matching code and required captcha confirm the account and show registration confirmation; without its ongoing confirmation session, this later visit does not sign it in.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Email confirmation"
          ],
          "to": "Confirmed",
          "from": "Unconfirmed"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionConfirmregistration"
    }
  ]
}
---

# Confirm email — Later confirmation — WP

## Trigger

Confirm email request: Later confirmation.

## Outcome

The matching code and required captcha confirm the account and show registration confirmation; without its ongoing confirmation session, this later visit does not sign it in.
