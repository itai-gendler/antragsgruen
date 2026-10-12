---
{
  "kind": "primary",
  "routes": {
    "route": "WA Save settings, including offline/online choice"
  },
  "steps": [
    {
      "text": "Change voting settings request: Save settings, including offline/online choice.",
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
      "text": "Ballot settings persist in supported phases; offline/online choice stays within this settings operation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Title",
            "Phase",
            "Answers",
            "Majority and quorum",
            "Participation policy",
            "Limits",
            "Publicity"
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

# Change voting settings — Save settings, including offline/online choice — WA

## Trigger

Change voting settings request: Save settings, including offline/online choice.

## Outcome

Ballot settings persist in supported phases; offline/online choice stays within this settings operation.
