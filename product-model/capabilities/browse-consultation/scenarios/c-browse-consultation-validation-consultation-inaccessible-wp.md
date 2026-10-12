---
{
  "kind": "validation",
  "routes": {
    "route": "WP Consultation inaccessible"
  },
  "steps": [
    {
      "text": "Browse consultation request: Consultation inaccessible.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
    },
    {
      "text": "The consultation access gate stops this request. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
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

# Browse consultation — Consultation inaccessible — WP

## Trigger

Browse consultation request: Consultation inaccessible.

## Outcome

The consultation access gate stops this request. This attempt does not complete the requested operation.
