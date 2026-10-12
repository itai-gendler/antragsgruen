---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-type",
      "effect": "reads",
      "facts": [
        "Names",
        "Amendment settings",
        "Flags"
      ],
      "contexts": [
        {
          "place": "web::public::consultation"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::consultation"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "user"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationMotionType.php"
    }
  ]
}
---

# Motion type read public is available to the applicable readers

Public metadata disclosure remains separate from administrative settings.
