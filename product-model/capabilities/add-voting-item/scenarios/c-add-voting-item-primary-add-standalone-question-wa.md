---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add standalone question"
  },
  "steps": [
    {
      "text": "Add voting item request: Add standalone question.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting-question",
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
          "place": "web::authenticated::voting-administration"
        }
      }
    },
    {
      "text": "Selected records are assigned or a standalone question is created through the same item-add operation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting-question",
          "effect": "creates",
          "facts": [
            "Text",
            "Voting association",
            "Result information",
            "Abstention"
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

# Add voting item — Add standalone question — WA

## Trigger

Add voting item request: Add standalone question.

## Outcome

A standalone Voting question is created and added to the Voting.
