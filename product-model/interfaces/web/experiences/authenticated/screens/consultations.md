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
    }
  ]
}
---

# Consultations

Site consultation catalogue, default selection and deletion/creation choices.
