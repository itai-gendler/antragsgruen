---
{
  "kind": "edge",
  "routes": {
    "route": "WA preparation clears votes"
  },
  "steps": [
    {
      "text": "Change voting settings request: preparation clears votes.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vote",
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
      "text": "Returning to Preparing clears votes and computed results.",
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
          "entity": "vote",
          "effect": "removes"
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

# Change voting settings — preparation clears votes — WA

## Trigger

Change voting settings request: preparation clears votes.

## Outcome

Returning to Preparing clears votes and computed results.
