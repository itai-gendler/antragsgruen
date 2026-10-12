---
{
  "kind": "primary",
  "routes": {
    "route": "WA Current target/attachments"
  },
  "steps": [
    {
      "text": "Read current debate request: Current target/attachments.",
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
      "text": "Current target and disclosed attachments are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": [
            "Target",
            "Start time",
            "End time",
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

# Read current debate — Current target/attachments — WA

## Trigger

Read current debate request: Current target/attachments.

## Outcome

Current target and disclosed attachments are returned.
