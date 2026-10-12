---
{
  "kind": "primary",
  "routes": {
    "route": "WA Close unpublished"
  },
  "steps": [
    {
      "text": "Close voting request: Close unpublished.",
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
      "text": "The ballot closes in the chosen publication state and computed item results are recorded separately from record disposition. The ballot is Closed-unpublished.",
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

# Close voting — Close unpublished — WA

## Trigger

Close voting request: Close unpublished.

## Outcome

The ballot closes in the chosen publication state and computed item results are recorded separately from document disposition. The ballot is Closed-unpublished.
