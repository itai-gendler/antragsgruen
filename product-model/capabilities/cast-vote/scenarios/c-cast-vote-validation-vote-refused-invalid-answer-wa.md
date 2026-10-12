---
{
  "kind": "validation",
  "routes": {
    "route": "WA Vote refused/invalid answer"
  },
  "steps": [
    {
      "text": "Cast vote request: Vote refused/invalid answer.",
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
      "text": "Ballot is not Open, answer is invalid, duplicate/abstention exists or configured maximum is reached. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Cast vote — Vote refused/invalid answer — WA

## Trigger

Cast vote request: Vote refused/invalid answer.

## Outcome

Ballot is not Open, answer is invalid, duplicate/abstention exists or configured maximum is reached. This attempt does not complete the requested operation.
