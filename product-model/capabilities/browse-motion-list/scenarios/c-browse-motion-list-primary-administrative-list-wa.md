---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative list"
  },
  "steps": [
    {
      "text": "Browse motion list request: Administrative list.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration-list"
        }
      }
    },
    {
      "text": "The administrative list presents summaries and applied filters with its actual route disclosure.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Title",
            "Address",
            "Text",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Protocol",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Relationships"
          ]
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Responsibility",
            "Voting information",
            "Internal note"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration-list"
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

# Browse motion list — Administrative list — WA

## Trigger

Browse motion list request: Administrative list.

## Outcome

The administrative list presents summaries and applied filters with its actual route disclosure.
