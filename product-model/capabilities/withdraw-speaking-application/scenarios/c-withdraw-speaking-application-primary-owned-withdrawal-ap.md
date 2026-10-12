---
{
  "kind": "primary",
  "routes": {
    "route": "AP Owned withdrawal"
  },
  "steps": [
    {
      "text": "Withdraw speaking application request: Owned withdrawal.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "The account/cookie-owned unstarted application is removed.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "antragsgruen-api::public"
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

# Withdraw speaking application — Owned withdrawal — AP

## Trigger

Withdraw speaking application request: Owned withdrawal.

## Outcome

The account/cookie-owned unstarted application is removed.
