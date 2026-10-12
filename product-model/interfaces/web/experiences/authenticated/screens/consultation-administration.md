---
{
  "entities": [
    {
      "entity": "site",
      "shows": [
        "Identity",
        "Default consultation",
        "Access settings",
        "Deleted"
      ]
    },
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
      ]
    },
    {
      "entity": "motion-type",
      "shows": [
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
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Site.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationMotionType.php"
    }
  ]
}
---

# Consultation administration

Consultation/site summary and type catalogue.
