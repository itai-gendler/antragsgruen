---
{
  "kind": "primary",
  "routes": {
    "route": "AA Published procedure"
  },
  "steps": [
    {
      "text": "Read proposed procedure request: Published procedure.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Published recommendations and alternatives are returned without ballot results or individual votes.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Version",
            "Recommendation",
            "Explanation",
            "Visibility time",
            "Notification information",
            "Proposer response",
            "Alternative text",
            "Deleted"
          ]
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Version",
            "Recommendation",
            "Explanation",
            "Visibility time",
            "Notification information",
            "Proposer response",
            "Alternative text",
            "Move destination",
            "Deleted"
          ]
        },
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": [
            "Contents",
            "Baseline",
            "Proposal association"
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
          "place": "antragsgruen-api::authenticated"
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
    }
  ]
}
---

# Read proposed procedure — Published procedure — AA

## Trigger

Read proposed procedure request: Published procedure.

## Outcome

Published recommendations and alternatives are returned without ballot results or individual votes.
