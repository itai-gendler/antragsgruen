---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove general abstention"
  },
  "steps": [
    {
      "text": "Revoke abstention request: Remove general abstention.",
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
      "text": "Owned general abstention is removed from Open; ordinary vote enumeration excludes this item.",
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

# Revoke abstention — Remove general abstention — WA

## Trigger

Revoke abstention request: Remove general abstention.

## Outcome

Owned general abstention is removed from Open; ordinary vote enumeration excludes this item.
