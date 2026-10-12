---
{
  "kind": "primary",
  "routes": {
    "route": "AA Administrative queue"
  },
  "steps": [
    {
      "text": "Read speaking-list administration request: Administrative queue.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Administrative queue settings, entries, slots and timing are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": [
            "Target",
            "Active",
            "Open flags",
            "Naming",
            "Timing"
          ]
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": [
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
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/ConsultationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/SpeechController.php"
    }
  ]
}
---

# Read speaking-list administration — Administrative queue — AA

## Trigger

Read speaking-list administration request: Administrative queue.

## Outcome

Administrative queue settings, entries, slots and timing are returned.
