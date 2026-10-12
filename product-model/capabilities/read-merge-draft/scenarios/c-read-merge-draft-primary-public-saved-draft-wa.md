---
{
  "kind": "primary",
  "routes": {
    "route": "WA Public saved draft"
  },
  "steps": [
    {
      "text": "Read merge draft request: Public saved draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::work-in-progress-draft"
        }
      }
    },
    {
      "text": "Public saved consolidation text, date and relevant amendments are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": [
            "Text",
            "Selections",
            "Handled warnings",
            "Dispositions",
            "Voting information",
            "Protocol",
            "Removed sections",
            "Publicity",
            "Saved date",
            "Deleted"
          ]
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::work-in-progress-draft"
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

# Read merge draft — Public saved draft — WA

## Trigger

Read merge draft request: Public saved draft.

## Outcome

Public saved consolidation text, date and relevant amendments are returned.
