---
{
  "kind": "primary",
  "routes": {
    "route": "AA Remove attachment"
  },
  "steps": [
    {
      "text": "Detach selected item selected item request: Remove attachment.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
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
          "place": "antragsgruen-api::authenticated"
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

# Detach debate voting — Remove attachment — AA

## Trigger

Detach debate voting request: Remove attachment.

## Outcome

The current debate's ballot attachment is removed.
