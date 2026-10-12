---
{
  "kind": "validation",
  "routes": {
    "route": "WA Change refused/invalid input"
  },
  "steps": [
    {
      "text": "Change speaking-list settings request: Change refused/invalid input.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    },
    {
      "text": "Queue/settings input or administration checks fail. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
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

# Change speaking-list settings — Change refused/invalid input — WA

## Trigger

Change speaking-list settings request: Change refused/invalid input.

## Outcome

Queue/settings input or administration checks fail. This attempt does not complete the requested operation.
