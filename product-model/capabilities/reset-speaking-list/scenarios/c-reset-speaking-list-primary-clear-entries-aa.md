---
{
  "kind": "primary",
  "routes": {
    "route": "AA Clear entries"
  },
  "steps": [
    {
      "text": "Reset selected queue request: Clear entries.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "The list's entries are removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
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

# Reset speaking list — Clear entries — AA

## Trigger

Reset speaking list request: Clear entries.

## Outcome

The list's entries are removed.
