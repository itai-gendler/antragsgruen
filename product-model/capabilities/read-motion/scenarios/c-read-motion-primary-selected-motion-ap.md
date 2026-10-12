---
{
  "kind": "primary",
  "routes": {
    "route": "AP Selected Motion"
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
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "The API returns Motion title/numbering, disposition/publication information, initiators/supporters, sections, disclosed proposed procedure and visible Amendment links.",
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
            "Relationships"
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
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Person information",
            "Organization",
            "Role",
            "Publicity"
          ]
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Title",
            "Disposition"
          ]
        },
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Recommendation",
            "Visibility time"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
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
      "target": "models/api/imotion/MotionDetails.php#fromEntity"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/imotion/Supporter.php#fromEntity"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/proposedprocedure/MotionProposedProcedure.php#fromMotion"
    }
  ]
}
---

# Read motion — Selected Motion — AP

## Trigger

Read motion request: Selected Motion.

## Outcome

The API returns Motion title/numbering, disposition/publication information, initiators/supporters, sections, disclosed proposed procedure and visible Amendment links.
