---
{
  "kind": "primary",
  "routes": {
    "route": "WA Owned withdrawal"
  },
  "steps": [
    {
      "text": "Withdraw speaking application request: Owned withdrawal.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list"
        }
      }
    },
    {
      "text": "The account/cookie-owned unstarted application is removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "removes"
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list"
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

# Withdraw speaking application — Owned withdrawal — WA

## Trigger

Withdraw speaking application request: Owned withdrawal.

## Outcome

The account/cookie-owned unstarted application is removed.
