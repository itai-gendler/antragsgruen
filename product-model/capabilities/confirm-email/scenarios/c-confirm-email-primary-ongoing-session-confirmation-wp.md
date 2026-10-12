---
{
  "kind": "primary",
  "routes": {
    "route": "WP Ongoing-session confirmation"
  },
  "steps": [
    {
      "text": "Confirm email request: Ongoing-session confirmation.",
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
      "text": "The matching code and required captcha confirm the pending account, establish its Web session, and show registration confirmation; managed access remains a separate access-request hand-off.",
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

# Confirm email — Ongoing-session confirmation — WP

## Trigger

Confirm email request: Ongoing-session confirmation.

## Outcome

The matching code and required captcha confirm the pending account, establish its Web session, and show registration confirmation; managed access remains a separate access-request hand-off.
