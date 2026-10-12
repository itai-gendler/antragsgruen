---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "reads",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "antragsgruen-api::public"
        }
      ],
      "facts": [
        "Public API"
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
      "target": "models/db/Consultation.php"
    }
  ]
}
---

# Consultation ordinary api is available to the applicable readers

Ordinary API requests first pass Base consultation access; their handler additionally requires enabled public API or authenticated identity. Page JSON uses session identity.
