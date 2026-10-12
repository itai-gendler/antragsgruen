---
{
  "kind": "edge",
  "routes": {
    "route": "WA Ballot fields unchanged outside supported phases"
  },
  "steps": [
    {
      "text": "Change voting settings request: Ballot fields unchanged outside supported phases.",
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
      "text": "Ballot fields remain unchanged outside supported editing phases.",
      "kind": "condition",
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

# Change voting settings — Ballot fields unchanged outside supported phases — WA

## Trigger

Change voting settings request: Ballot fields unchanged outside supported phases.

## Outcome

Ballot fields remain unchanged outside supported editing phases.
