---
{
  "kind": "primary",
  "routes": {
    "route": "WA Request and confirm"
  },
  "steps": [
    {
      "text": "Change email request: Request and confirm.",
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
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "The Product saves the requested replacement and sends its confirmation message.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Pending email change"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "The Product reads the pending destination for the email confirmation message.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Pending email change"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "The User follows the replacement-email confirmation link.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Pending email change"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "A valid replacement email is saved as the pending change. The confirmation message goes to that pending destination; following its matching code replaces Email, marks Email confirmation, and clears Pending email change. The local Authentication identity remains unchanged by changeEmailAddress.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Pending email change",
            "Email",
            "Email confirmation"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
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
      "target": "models/db/User.php#sendEmailChangeMail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php#changeEmailAddress"
    }
  ]
}
---

# Change email — Request and confirm — WA

## Trigger

Change email request: Request and confirm.

## Outcome

A valid replacement email is saved as the pending change. The confirmation message goes to that pending destination; following its matching code replaces Email, marks Email confirmation, and clears Pending email change. The local Authentication identity remains unchanged by changeEmailAddress.
