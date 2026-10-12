---
{
  "kind": "primary",
  "routes": {
    "route": "WA Create/activate queue"
  },
  "steps": [
    {
      "text": "Activate debate selected queue request: Create/activate queue.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    },
    {
      "text": "A queue is created or activated and attached to the current debate.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "creates",
          "facts": [
            "Target",
            "Active",
            "Open flags",
            "Naming",
            "Timing"
          ]
        },
        {
          "entity": "debate",
          "effect": "changes",
          "facts": [
            "Attachments"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/DebateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/DebateTools.php"
    }
  ]
}
---

# Activate debate speaking list — Create/activate queue — WA

## Trigger

Activate debate speaking list request: Create/activate queue.

## Outcome

A queue is created or activated and attached to the current debate.
