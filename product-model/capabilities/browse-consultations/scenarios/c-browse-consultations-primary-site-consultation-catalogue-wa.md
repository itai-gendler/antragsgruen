---
{
  "kind": "primary",
  "routes": {
    "route": "WA Site consultation catalogue"
  },
  "steps": [
    {
      "text": "Browse consultations request: Site consultation catalogue.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
        }
      }
    },
    {
      "text": "The site consultation catalogue and selected default are presented.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Identity",
            "Default consultation",
            "Access settings",
            "Deleted"
          ]
        },
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
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

# Browse consultations — Site consultation catalogue — WA

## Trigger

Browse consultations request: Site consultation catalogue.

## Outcome

The site consultation catalogue and selected default are presented.
