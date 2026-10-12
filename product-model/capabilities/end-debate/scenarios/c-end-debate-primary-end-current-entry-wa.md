---
{
  "kind": "primary",
  "routes": {
    "route": "WA End current entry"
  },
  "steps": [
    {
      "text": "End debate request: End current entry.",
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
      "text": "Current debate receives end time and is no longer current.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "changes",
          "facts": [
            "End time"
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

# End debate — End current entry — WA

## Trigger

End debate request: End current entry.

## Outcome

Current debate receives end time and is no longer current.
