---
{
  "kind": "validation",
  "routes": {
    "route": "WA Attachment refused"
  },
  "steps": [
    {
      "text": "Attach debate selected item request: Attachment refused.",
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
      "text": "Ballot/target is invalid. This attempt does not complete the requested operation.",
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

# Attach debate voting — Attachment refused — WA

## Trigger

Attach debate voting request: Attachment refused.

## Outcome

Ballot/target is invalid. This attempt does not complete the requested operation.
