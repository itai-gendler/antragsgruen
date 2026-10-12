---
{
  "kind": "validation",
  "routes": {
    "route": "WA Results unavailable"
  },
  "steps": [
    {
      "text": "Read voting results request: Results unavailable.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting-question",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-results"
        }
      }
    },
    {
      "text": "The result is unavailable or undisclosed. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting-question",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-results"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/ConsultationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/VotingController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/voting/VotingPayloadBuilder.php"
    }
  ]
}
---

# Read voting results — Results unavailable — WA

## Trigger

Read voting results request: Results unavailable.

## Outcome

The result is unavailable or undisclosed. This attempt does not complete the requested operation.
