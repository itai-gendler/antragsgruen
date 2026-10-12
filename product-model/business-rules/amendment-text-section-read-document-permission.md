---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-text-section",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::amendment"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "web::public::amendment"
        },
        {
          "place": "web::public::consultation"
        },
        {
          "place": "web::authenticated::consultation"
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
      "target": "models/db/AmendmentSection.php"
    }
  ]
}
---

# Amendment text section read document is available to the applicable readers

Direct document reading additionally preserves active/public section disclosure and the applicable document access gate.
