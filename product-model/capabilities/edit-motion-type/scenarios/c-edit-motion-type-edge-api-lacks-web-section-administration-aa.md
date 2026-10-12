---
{
  "kind": "edge",
  "routes": {
    "route": "AA API lacks Web section administration"
  },
  "steps": [
    {
      "text": "Edit type request: API lacks Web section administration.",
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
      "text": "An API update saves type metadata and settings and returns their updated projection; the request contract has no section-definition collection editing, so existing sections remain unchanged.",
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

# Edit motion type — API lacks Web section administration — AA

## Trigger

Edit motion type request: API lacks Web section administration.

## Outcome

API metadata/settings does not administer the Web section-definition collection.
