---
{
  "kind": "primary",
  "routes": {
    "route": "WA Close published"
  },
  "steps": [
    {
      "text": "Close voting request: Close published.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting-question",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-administration"
        }
      }
    },
    {
      "text": "The ballot closes in the chosen publication state and computed item results are recorded separately from record disposition. The ballot is Closed-published.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Phase"
          ]
        },
        {
          "entity": "voting-question",
          "effect": "changes",
          "facts": [
            "Result information"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/VotingController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/VotingMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/voting/VotingPayloadBuilder.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/VotingController.php"
    }
  ]
}
---

# Close voting — Close published — WA

## Trigger

Close voting request: Close published.

## Outcome

The ballot closes in the chosen publication state and computed item results are recorded separately from document disposition. The ballot is Closed-published.
