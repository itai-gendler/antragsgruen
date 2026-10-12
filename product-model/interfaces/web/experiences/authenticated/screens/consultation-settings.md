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
        "Participation settings",
        "Display settings"
      ]
    },
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
      "entity": "tag",
      "shows": [
        "Name",
        "Order",
        "Classification",
        "Document associations"
      ],
      "collects": [
        "Name",
        "Order",
        "Classification"
      ]
    },
    {
      "entity": "speaking-list",
      "shows": [
        "Target",
        "Active",
        "Open flags",
        "Naming",
        "Timing"
      ]
    },
    {
      "entity": "speaking-subqueue",
      "shows": [
        "Name",
        "Order",
        "Speaking list"
      ],
      "collects": [
        "Name",
        "Order"
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
      "target": "models/db/Site.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationSettingsTag.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechSubqueue.php"
    }
  ]
}
---

# Consultation settings

Access/participation, behavioral display/speaking settings, tags and subqueue configuration.
