---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative type catalogue"
  },
  "steps": [
    {
      "text": "Browse type settings request: Administrative type catalogue.",
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
      "text": "The administrative type catalogue is presented.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Screening",
            "Amendment settings",
            "Flags",
            "Deleted"
          ]
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

# Browse motion-type settings — Administrative type catalogue — WA

## Trigger

Browse motion-type settings request: Administrative type catalogue.

## Outcome

The administrative type catalogue is presented.
