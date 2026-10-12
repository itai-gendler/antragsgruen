---
{
  "kind": "primary",
  "routes": {
    "route": "AA Catalogue"
  },
  "steps": [
    {
      "text": "Browse consultation request: Catalogue.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
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
      "text": "Requested consultation summaries, agenda and record catalogue are returned; Web search/filter choices narrow that catalogue.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": [
            "Title",
            "Language",
            "Participation settings",
            "Display settings",
            "Wording base",
            "Lifecycle dates",
            "Deleted",
            "Public API"
          ]
        },
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": [
            "Code",
            "Title",
            "Hierarchy",
            "Timing",
            "Procedure inclusion",
            "Associated type",
            "Speaking resources"
          ]
        },
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

# Browse consultation — Catalogue — AA

## Trigger

Browse consultation request: Catalogue.

## Outcome

Requested consultation summaries, agenda and document catalogue are returned; Web search/filter choices narrow that catalogue.
