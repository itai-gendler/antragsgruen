---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove selected participant"
  },
  "steps": [
    {
      "text": "Remove voter from group request: Remove selected participant.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
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
      "text": "Participant-group membership is removed through the voting operation's group/site/self checks.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
          "effect": "removes"
        },
        {
          "entity": "site",
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

# Remove voter from group — Remove selected participant — WA

## Trigger

Remove voter from group request: Remove selected participant.

## Outcome

Participant-group membership is removed through the voting operation's group/site/self checks.
