---
{
  "entities": [
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
    },
    {
      "entity": "section-definition",
      "shows": [
        "Section identity",
        "Kind",
        "Title",
        "Order",
        "Languages",
        "Requirements",
        "Publicity",
        "Editability",
        "Removed"
      ]
    },
    {
      "entity": "motion",
      "shows": [
        "Title",
        "Address",
        "Text",
        "Initiators",
        "Disposition",
        "Submission information",
        "Flags",
        "Protocol",
        "Responsibility",
        "Voting information",
        "Internal note",
        "Relationships"
      ],
      "collects": [
        "Title",
        "Text",
        "Initiators"
      ]
    },
    {
      "entity": "motion-text-section",
      "shows": [
        "Section identity",
        "Language",
        "Content",
        "Activity",
        "Publicity"
      ]
    },
    {
      "entity": "supporter",
      "shows": [
        "Target",
        "Role",
        "Identity",
        "Person information",
        "Organization",
        "Contact",
        "Order",
        "Gender",
        "Publicity",
        "Resolution date"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationMotionType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationSettingsMotionSection.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionSection.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ISupporter.php"
    }
  ]
}
---

# Motion submission

One creation/edit/confirmation process with sections, initiators, saved draft and preview.
