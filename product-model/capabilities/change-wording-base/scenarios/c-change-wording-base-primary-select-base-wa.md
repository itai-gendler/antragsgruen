---
{
  "kind": "primary",
  "routes": {
    "route": "WA Select base"
  },
  "steps": [
    {
      "text": "Change wording base request: Select base.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::translation-wording"
        }
      }
    },
    {
      "text": "Selected base wording persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "changes",
          "facts": [
            "Wording base"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::translation-wording"
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

# Change wording base — Select base — WA

## Trigger

Change wording base request: Select base.

## Outcome

Selected base wording persists.
