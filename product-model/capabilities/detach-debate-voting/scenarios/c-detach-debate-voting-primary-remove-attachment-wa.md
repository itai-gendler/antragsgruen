---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove attachment"
  },
  "steps": [
    {
      "text": "Detach debate selected item request: Remove attachment.",
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
      "text": "The current debate's ballot attachment is removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
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

# Detach debate voting — Remove attachment — WA

## Trigger

Detach debate voting request: Remove attachment.

## Outcome

The current debate's ballot attachment is removed.
