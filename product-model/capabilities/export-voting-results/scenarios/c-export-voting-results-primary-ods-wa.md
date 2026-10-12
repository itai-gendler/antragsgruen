---
{
  "kind": "primary",
  "routes": {
    "route": "WA ODS"
  },
  "steps": [
    {
      "text": "Export voting results request: ODS.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting-question",
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
      "text": "The voting result export returns ODS, including its implemented individual-vote projection.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": [
            "Title",
            "Phase",
            "Order",
            "Assignments",
            "Answers",
            "Majority and quorum",
            "Participation policy",
            "Limits",
            "Publicity",
            "Opening snapshot"
          ]
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": [
            "Account",
            "Voting and item",
            "Answer",
            "Weight",
            "Time",
            "Retained publicity"
          ]
        },
        {
          "entity": "voting-question",
          "effect": "reads",
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

# Export voting results — ODS — WA

## Trigger

Export voting results request: ODS.

## Outcome

The voting result export returns ODS, including its implemented individual-vote projection.
