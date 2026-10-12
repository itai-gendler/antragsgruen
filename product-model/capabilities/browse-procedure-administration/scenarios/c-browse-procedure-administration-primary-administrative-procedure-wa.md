---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative procedure"
  },
  "steps": [
    {
      "text": "Browse procedure administration request: Administrative procedure.",
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
          "entity": "procedure-note",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
        }
      }
    },
    {
      "text": "Administrative procedure, proposer response, responsibility and staff notes are presented.",
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
          "entity": "procedure-note",
          "effect": "reads",
          "facts": [
            "Author",
            "Target",
            "Text",
            "Creation time"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
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

# Browse procedure administration — Administrative procedure — WA

## Trigger

Browse procedure administration request: Administrative procedure.

## Outcome

Administrative procedure, proposer response, responsibility and staff notes are presented.
