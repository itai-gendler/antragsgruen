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
      "type": "entity",
      "id": "voting-activity"
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

# Inspected voting phase operations record visible voting activity.

Opening, closing, reopening and reset record their actual visible voting activity with actor/time/details. The phase effect does not author an incidental log mutation Step.
