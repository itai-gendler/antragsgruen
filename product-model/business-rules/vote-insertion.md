---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "cast-vote",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "abstain-from-voting",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
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

# Votes retain server-selected weight and validated answers without silent overwrite.

Vote insertion selects weight from the acting account’s consultation configuration, checks the configured answer and highest applicable/default group maximum, rejects duplicates and respects mutual exclusion with general abstention. It does not silently update an earlier vote.
