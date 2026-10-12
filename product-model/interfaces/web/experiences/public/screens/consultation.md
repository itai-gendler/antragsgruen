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
      ]
    },
    {
      "entity": "agenda-item",
      "shows": [
        "Code",
        "Title",
        "Hierarchy",
        "Timing",
        "Procedure inclusion",
        "Associated type",
        "Speaking resources"
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
      ]
    },
    {
      "entity": "activity-entry",
      "shows": [
        "Operation",
        "Actor",
        "Target",
        "Time",
        "Details"
      ]
    },
    {
      "entity": "debate",
      "shows": [
        "Target",
        "Start time",
        "End time",
        "Attachments"
      ]
    },
    {
      "entity": "motion-type",
      "shows": [
        "Names",
        "Amendment settings",
        "Flags"
      ]
    },
    {
      "entity": "speaking-list",
      "shows": [
        "Target",
        "Active",
        "Open flags"
      ]
    },
    {
      "entity": "voting",
      "shows": [
        "Title",
        "Phase",
        "Assignments"
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
      "target": "models/db/ConsultationAgendaItem.php"
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
      "target": "models/db/ConsultationLog.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/DebateItem.php"
    }
  ]
}
---

# Consultation

Consultation/access information, agenda, summaries, search/filter results, activity and current debate.
