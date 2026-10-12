---
{
  "kind": "validation",
  "routes": {
    "route": "WA Addition refused/invalid input"
  },
  "steps": [
    {
      "text": "Add section definition request: Addition refused/invalid input.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
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
      "text": "Section input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
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

# Add section definition — Addition refused/invalid input — WA

## Trigger

Add section definition request: Addition refused/invalid input.

## Outcome

Section input is invalid. This attempt does not complete the requested operation.
