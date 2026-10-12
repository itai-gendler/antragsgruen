---
{
  "entities": [
    {
      "entity": "consultation",
      "shows": [
        "Title",
        "Language",
        "Participation settings",
        "Display settings",
        "Wording base",
        "Lifecycle dates",
        "Deleted",
        "Public API"
      ],
      "collects": [
        "Wording base"
      ]
    },
    {
      "entity": "wording-override",
      "shows": [
        "Phrase",
        "Replacement"
      ],
      "collects": [
        "Phrase",
        "Replacement"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationText.php"
    }
  ]
}
---

# Translation / Wording

Selected wording base and addressed phrase replacements.
