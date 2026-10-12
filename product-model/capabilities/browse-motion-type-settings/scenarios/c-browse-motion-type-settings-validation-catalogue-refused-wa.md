---
{
  "kind": "validation",
  "routes": {
    "route": "WA Catalogue refused"
  },
  "steps": [
    {
      "text": "Browse type settings request: Catalogue refused.",
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
          "place": "web::authenticated::consultation-administration"
        }
      }
    },
    {
      "text": "The catalogue entry check stops this request. This attempt does not complete the requested operation.",
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
          "place": "web::authenticated::consultation-administration"
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

# Browse motion-type settings — Catalogue refused — WA

## Trigger

Browse motion-type settings request: Catalogue refused.

## Outcome

The catalogue entry check stops this request. This attempt does not complete the requested operation.
