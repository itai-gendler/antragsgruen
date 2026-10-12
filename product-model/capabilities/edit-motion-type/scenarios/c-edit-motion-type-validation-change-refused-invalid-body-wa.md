---
{
  "kind": "validation",
  "routes": {
    "route": "WA Change refused/invalid body"
  },
  "steps": [
    {
      "text": "Edit type request: Change refused/invalid body.",
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
          "place": "web::authenticated::motion-type"
        }
      }
    },
    {
      "text": "Body/settings input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
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
          "place": "web::authenticated::motion-type"
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

# Edit motion type — Change refused/invalid body — WA

## Trigger

Edit motion type request: Change refused/invalid body.

## Outcome

Body/settings input is invalid. This attempt does not complete the requested operation.
