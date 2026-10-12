---
{
  "kind": "primary",
  "routes": {
    "route": "WP Motion PDF"
  },
  "steps": [
    {
      "text": "Export record request: Motion PDF.",
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
      "text": "The selected Motion PDF projection is returned.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Title",
            "Text",
            "Initiators",
            "Relationships",
            "Disposition",
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
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Person information",
            "Organization",
            "Role",
            "Publicity",
            "Resolution date"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionExportTraits.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "views/motion/LayoutHelper.php"
    }
  ]
}
---

# Export document — Motion PDF — WP

## Trigger

Export document request: Motion PDF.

## Outcome

The selected Motion PDF projection is returned.
