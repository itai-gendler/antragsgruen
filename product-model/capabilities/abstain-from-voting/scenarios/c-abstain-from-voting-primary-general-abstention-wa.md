---
{
  "kind": "primary",
  "routes": {
    "route": "WA General abstention"
  },
  "steps": [
    {
      "text": "Abstain from voting request: General abstention.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "vote",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::votings"
        }
      }
    },
    {
      "text": "A general-abstention vote persists only when no ordinary item votes exist.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "vote",
          "effect": "creates",
          "facts": [
            "Account",
            "Voting and item",
            "Answer",
            "Weight",
            "Time",
            "Retained publicity"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::votings"
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

# Abstain from voting — General abstention — WA

## Trigger

Abstain from voting request: General abstention.

## Outcome

A general-abstention vote persists only when no ordinary item votes exist.
