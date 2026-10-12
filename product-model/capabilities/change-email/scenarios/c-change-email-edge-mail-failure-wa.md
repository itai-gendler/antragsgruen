---
{
  "kind": "edge",
  "routes": {
    "route": "WA mail failure"
  },
  "steps": [
    {
      "text": "Change email request: mail failure.",
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
      "text": "Replacement-email mail failure is reported before sendEmailChangeMail saves the new pending destination. The previously persisted Email and Pending email change remain unchanged; other valid account-form edits may already have saved.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email",
            "Pending email change"
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
    }
  ]
}
---

# Change email — mail failure — WA

## Trigger

Change email request: mail failure.

## Outcome

Replacement-email mail failure is reported before sendEmailChangeMail saves the new pending destination. The previously persisted Email and Pending email change remain unchanged; other valid account-page edits may already have saved.
