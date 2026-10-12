---
{
  "kind": "primary",
  "routes": {
    "route": "AA API metadata and settings"
  },
  "steps": [
    {
      "text": "Edit type request: API metadata and settings.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
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
      "text": "Type metadata/settings persist; Web section definitions remain independently editable, without API parity.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "changes",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Screening",
            "Amendment settings",
            "Flags"
          ]
        },
        {
          "entity": "section-definition",
          "effect": "reads",
          "facts": []
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
      "target": "controllers/admin/IndexController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/MotionTypeController.php#actionUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/motionType/MotionTypeUpdateRequest.php"
    }
  ]
}
---

# Edit motion type — API metadata and settings — AA

## Trigger

Edit motion type request: API metadata and settings.

## Outcome

Type metadata/settings persist; Web section definitions remain independently editable, without API parity.
