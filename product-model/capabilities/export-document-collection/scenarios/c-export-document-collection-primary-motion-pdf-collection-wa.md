---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion PDF collection"
  },
  "steps": [
    {
      "text": "Export record collection request: Motion PDF collection.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    },
    {
      "text": "The selected Motion PDF collection is rendered from readable source records.",
      "kind": "product",
      "actor": "user",
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
          "entity": "amendment",
          "effect": "reads",
          "facts": []
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
          "place": "web::authenticated::consultation"
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

# Export document collection — Motion PDF collection — WA

## Trigger

Export document collection request: Motion PDF collection.

## Outcome

The selected Motion PDF collection is rendered from readable source records.
