---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "open-voting",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "close-voting",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "reset-voting",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-voting-settings",
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

# Closing, reopening and resetting retain distinct vote/result effects.

Closing stores computed item results and chosen publication phase; reopening retains vote rows. Reset/preparation clears votes and results. Offline configuration uses its actual snapshot/retention behavior; ballot result is not document disposition.
