---
{
  "kind": "primary",
  "routes": {
    "route": "WA Save order"
  },
  "steps": [
    {
      "text": "Reorder votings request: Save order.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
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
      "text": "Submitted ballot order persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Order"
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

# Reorder votings — Save order — WA

## Trigger

Reorder votings request: Save order.

## Outcome

Submitted ballot order persists.
