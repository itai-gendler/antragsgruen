---
{
  "kind": "primary",
  "routes": {
    "route": "AA Public metadata"
  },
  "steps": [
    {
      "text": "Read types request: Public metadata.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Public type metadata is returned with its actual public projection.",
      "kind": "product",
      "actor": "user",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/MotionTypeController.php"
    }
  ]
}
---

# Read motion types — Public metadata — AA

## Trigger

Read motion types request: Public metadata.

## Outcome

Public type metadata is returned with its actual public projection.
