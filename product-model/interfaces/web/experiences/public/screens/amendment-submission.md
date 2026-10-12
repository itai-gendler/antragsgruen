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
        "Protocol",
        "Voting information",
        "Relationships"
      ]
    },
    {
      "entity": "amendment",
      "shows": [
        "Base",
        "Title",
        "Changes",
        "Reason",
        "Alternative information",
        "Initiators",
        "Disposition",
        "Submission information",
        "Voting information"
      ],
      "collects": [
        "Changes",
        "Reason",
        "Initiators"
      ]
    },
    {
      "entity": "amendment-text-section",
      "shows": [
        "Section identity",
        "Language",
        "Proposed content",
        "Baseline"
      ]
    },
    {
      "entity": "supporter",
      "shows": [
        "Role",
        "Person information",
        "Organization",
        "Publicity"
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
      "target": "models/db/Amendment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentSection.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ISupporter.php"
    }
  ]
}
---

# Amendment submission

One creation/edit/confirmation process with base/parent text, changes, reason, initiators, saved draft and preview.
