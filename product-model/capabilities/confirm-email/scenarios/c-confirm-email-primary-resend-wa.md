---
{
  "kind": "primary",
  "routes": {
    "route": "WA Resend"
  },
  "steps": [
    {
      "text": "Confirm email request: Resend.",
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
      "text": "The Product reads the saved destination before sending the renewed confirmation code.",
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
          "place": "web::authenticated::email-confirmation"
        }
      }
    },
    {
      "text": "The existing pending account remains Unconfirmed; its date-based confirmation code is mailed again to its saved address and the confirmation form remains available. Successful sending saves the resend timing.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password configuration"
          ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/LoginUsernamePasswordForm.php#sendConfirmationEmail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php#createEmailConfirmationCode"
    }
  ]
}
---

# Confirm email — Resend — WA

## Trigger

Confirm email request: Resend.

## Outcome

The existing pending account remains Unconfirmed; its date-based confirmation code is mailed again to its saved address and the confirmation form remains available. Successful sending saves the resend timing.
