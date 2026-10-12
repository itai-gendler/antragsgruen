---
{
  "kind": "validation",
  "routes": {
    "route": "WA Detachment refused"
  },
  "steps": [
    {
      "text": "Detach debate selected item request: Detachment refused.",
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
      "text": "Attachment/target is unavailable. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Detach debate voting — Detachment refused — WA

## Trigger

Detach debate voting request: Detachment refused.

## Outcome

Attachment/target is unavailable. This attempt does not complete the requested operation.
