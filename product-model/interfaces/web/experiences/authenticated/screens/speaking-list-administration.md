---
{
  "entities": [
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
      ]
    },
    {
      "entity": "speech",
      "shows": [
        "Identity",
        "Name",
        "Subqueue",
        "Point of order",
        "Application order",
        "Slot",
        "Start time",
        "Stop time"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechSubqueue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueueItem.php"
    }
  ]
}
---

# Speaking-list administration

Queue settings, applications, slots, order and timing operations.
