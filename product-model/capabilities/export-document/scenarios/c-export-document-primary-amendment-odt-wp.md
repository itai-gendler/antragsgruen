---
{
  "kind": "primary",
  "routes": {
    "route": "WP Amendment ODT"
  },
  "steps": [
    {
      "text": "Export record request: Amendment ODT.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
        }
      }
    },
    {
      "text": "The selected Amendment ODT projection is returned.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": [
            "Section identity",
            "Language",
            "Proposed content",
            "Baseline"
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
          "place": "web::public::amendment"
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
      "target": "views/amendment/LayoutHelper.php"
    }
  ]
}
---

# Export document — Amendment ODT — WP

## Trigger

Export document request: Amendment ODT.

## Outcome

The selected Amendment ODT projection is returned.
