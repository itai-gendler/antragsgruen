---
{
  "kind": "validation",
  "routes": {
    "route": "WA Abstention refused"
  },
  "steps": [
    {
      "text": "Abstain from voting request: Abstention refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "vote",
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
          "place": "web::authenticated::votings"
        }
      }
    },
    {
      "text": "Abstention is unconfigured, an ordinary vote exists or ballot is not Open. This attempt does not complete the requested operation.",
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

# Abstain from voting — Abstention refused — WA

## Trigger

Abstain from voting request: Abstention refused.

## Outcome

Abstention is unconfigured, an ordinary vote exists or ballot is not Open. This attempt does not complete the requested operation.
