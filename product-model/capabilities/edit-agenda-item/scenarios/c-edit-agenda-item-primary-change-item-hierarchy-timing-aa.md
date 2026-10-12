---
{
  "kind": "primary",
  "routes": {
    "route": "AA Change item/hierarchy/timing"
  },
  "steps": [
    {
      "text": "Edit agenda item request: Change item/hierarchy/timing.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
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
      "text": "Valid recursive saving updates title/code, hierarchy, time and associated type.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "changes",
          "facts": [
            "Code",
            "Title",
            "Hierarchy",
            "Timing",
            "Procedure inclusion",
            "Associated type",
            "Speaking resources"
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
    }
  ]
}
---

# Edit agenda item — Change item/hierarchy/timing — AA

## Trigger

Edit agenda item request: Change item/hierarchy/timing.

## Outcome

Valid recursive saving updates title/code, hierarchy, time and associated type.
