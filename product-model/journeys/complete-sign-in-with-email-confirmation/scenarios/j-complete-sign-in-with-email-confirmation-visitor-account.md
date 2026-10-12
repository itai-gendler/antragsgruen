---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "Visitor Account"
  },
  "steps": [
    {
      "text": "Sign in request: Email-confirmation hand-off.",
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
      },
      "capability": "sign-in"
    },
    {
      "text": "Credential verification retains the pending Account and carries the actor to email confirmation.",
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
      },
      "capability": "sign-in"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::email-confirmation"
        }
      },
      "capability": "sign-in"
    },
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
      },
      "capability": "confirm-email"
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
      },
      "capability": "confirm-email"
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

# Complete sign-in with email confirmation — Visitor — Account

## Trigger

Complete sign-in’s required email confirmation.

## Outcome

The pending target email is confirmed and the authentication continuation completes.
