---
{
  "kind": "validation",
  "routes": {
    "route": "WP Withdrawal refused"
  },
  "steps": [
    {
      "text": "Withdraw speaking application request: Withdrawal refused.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::speaking-list"
        }
      }
    },
    {
      "text": "The application is absent or already started. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::speaking-list"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/SpeechController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    }
  ]
}
---

# Withdraw speaking application — Withdrawal refused — WP

## Trigger

Withdraw speaking application request: Withdrawal refused.

## Outcome

The application is absent or already started. This attempt does not complete the requested operation.
