---
{
  "kind": "primary",
  "routes": {
    "route": "WA Undo owned item/group vote"
  },
  "steps": [
    {
      "text": "Withdraw vote request: Undo owned item/group vote.",
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
      "text": "Owned item/group votes are removed from an Open ballot without a fresh participation-policy check.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "vote",
          "effect": "removes"
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

# Withdraw vote — Undo owned item/group vote — WA

## Trigger

Withdraw vote request: Undo owned item/group vote.

## Outcome

Owned item/group votes are removed from an Open ballot without a fresh participation-policy check.
