---
{
  "kind": "primary",
  "routes": {
    "route": "WA Preparation and vote clearing"
  },
  "steps": [
    {
      "text": "Reset voting request: Preparation and vote clearing.",
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
      "text": "The ballot returns to Preparing; vote rows and computed results are cleared.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Phase"
          ]
        },
        {
          "entity": "vote",
          "effect": "removes"
        },
        {
          "entity": "voting-question",
          "effect": "changes",
          "facts": [
            "Result information"
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

# Reset voting — Preparation and vote clearing — WA

## Trigger

Reset voting request: Preparation and vote clearing.

## Outcome

The ballot returns to Preparing; vote rows and computed results are cleared.
