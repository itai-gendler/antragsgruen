---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-text-section",
      "effect": "reads",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::motion"
        },
        {
          "place": "web::public::motion"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "web::authenticated::consultation"
        },
        {
          "place": "web::public::consultation"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "consultation"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionSection.php"
    }
  ]
}
---

# Motion text section read document is available to the applicable readers

Direct document reading additionally preserves active/public section disclosure and the applicable document access gate.
