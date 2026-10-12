---
{
  "kind": "validation",
  "routes": {
    "route": "WA Ending refused"
  },
  "steps": [
    {
      "text": "End debate request: Ending refused.",
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
      "text": "Current entry/end request is unavailable. This attempt does not complete the requested operation.",
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

# End debate — Ending refused — WA

## Trigger

End debate request: Ending refused.

## Outcome

Current entry/end request is unavailable. This attempt does not complete the requested operation.
