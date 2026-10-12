---
{
  "kind": "primary",
  "routes": {
    "route": "WP Selected Motion"
  },
  "steps": [
    {
      "text": "Read motion request: Selected Motion.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
        }
      }
    },
    {
      "text": "Selected contents, participants and disclosed procedure are returned.",
      "kind": "product",
      "actor": "visitor",
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
            "Protocol",
            "Voting information",
            "Relationships",
            "Public tags"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": [
            "Section identity",
            "Language",
            "Content",
            "Activity",
            "Publicity"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
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

# Read motion — Selected Motion — WP

## Trigger

Read motion request: Selected Motion.

## Outcome

Selected contents, participants and disclosed procedure are returned.
