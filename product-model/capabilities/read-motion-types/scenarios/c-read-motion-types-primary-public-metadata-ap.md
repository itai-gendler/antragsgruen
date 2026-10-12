---
{
  "kind": "primary",
  "routes": {
    "route": "AP Public metadata"
  },
  "steps": [
    {
      "text": "Read types request: Public metadata.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "Public type metadata is returned with its actual public projection.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": [
            "Names",
            "Amendment settings",
            "Flags"
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
      "target": "controllers/rest/MotionTypeController.php"
    }
  ]
}
---

# Read motion types — Public metadata — AP

## Trigger

Read motion types request: Public metadata.

## Outcome

Public type metadata is returned with its actual public projection.
