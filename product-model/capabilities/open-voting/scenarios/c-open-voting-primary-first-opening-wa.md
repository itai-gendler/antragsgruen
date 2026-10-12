---
{
  "kind": "primary",
  "routes": {
    "route": "WA First opening"
  },
  "steps": [
    {
      "text": "Open voting request: First opening.",
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
      "text": "First opening sets Phase to Open, initializes any unset voting defaults, and saves the first-opening publicity snapshot.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Phase",
            "Opening snapshot"
          ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php#openVoting"
    }
  ]
}
---

# Open voting — First opening — WA

## Trigger

Open voting request: First opening.

## Outcome

First opening sets Phase to Open, initializes any unset voting defaults, and saves the first-opening publicity snapshot.
