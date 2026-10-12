---
{
  "kind": "primary",
  "routes": {
    "route": "WA Item/configured item-group vote"
  },
  "steps": [
    {
      "text": "Cast vote request: Item/configured item-group vote.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "vote",
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
      "text": "A valid answer inserts a vote with server-selected weight and retained publicity; duplicates are refused without overwriting.",
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

# Cast vote — Item/configured item-group vote — WA

## Trigger

Cast vote request: Item/configured item-group vote.

## Outcome

A valid answer inserts a vote with server-selected weight and retained publicity; duplicates are refused without overwriting.
