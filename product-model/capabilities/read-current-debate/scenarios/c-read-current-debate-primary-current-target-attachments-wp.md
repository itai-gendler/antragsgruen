---
{
  "kind": "primary",
  "routes": {
    "route": "WP Current target/attachments"
  },
  "steps": [
    {
      "text": "Read current debate request: Current target/attachments.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
    },
    {
      "text": "Current target and disclosed attachments are returned.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "web::public::consultation"
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

# Read current debate — Current target/attachments — WP

## Trigger

Read current debate request: Current target/attachments.

## Outcome

Current target and disclosed attachments are returned.
