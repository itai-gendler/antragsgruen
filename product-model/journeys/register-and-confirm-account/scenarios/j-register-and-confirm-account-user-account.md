---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Account"
  },
  "steps": [
    {
      "text": "Create account request: Unconfirmed.",
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
      },
      "capability": "create-account"
    },
    {
      "text": "The new local account is saved Unconfirmed, its confirmation message is sent, and the pending sign-in hands off to email confirmation.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "create-account"
    },
    {
      "text": "The Product sends the confirmation message to the saved account address.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email",
            "Email confirmation"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "create-account"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::email-confirmation"
        }
      },
      "capability": "create-account"
    },
    {
      "text": "Confirm email request: Ongoing-session confirmation.",
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
      },
      "capability": "confirm-email"
    },
    {
      "text": "The matching code and required captcha confirm the pending account, establish its Web session, and show registration confirmation; managed access remains a separate access-request hand-off.",
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
          "place": "web::authenticated::email-confirmation"
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
      "target": "controllers/UserController.php#actionLogin"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionConfirmregistration"
    }
  ]
}
---

# Register and confirm account — User — Account

## Trigger

Complete a newly created account’s email confirmation.

## Outcome

The new account email is confirmed.
