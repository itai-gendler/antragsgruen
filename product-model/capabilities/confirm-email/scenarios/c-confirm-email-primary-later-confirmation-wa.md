---
{
  "kind": "primary",
  "routes": {
    "route": "WA Later confirmation"
  },
  "steps": [
    {
      "text": "Confirm email request: Later confirmation.",
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
          "place": "web::authenticated::email-confirmation"
        }
      }
    },
    {
      "text": "The matching code and required captcha confirm the account and show registration confirmation; without its ongoing confirmation session, this later visit does not sign it in.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::email-confirmation"
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

# Confirm email — Later confirmation — WA

## Trigger

Confirm email request: Later confirmation.

## Outcome

The matching code and required captcha confirm the account and show registration confirmation; without its ongoing confirmation session, this later visit does not sign it in.
