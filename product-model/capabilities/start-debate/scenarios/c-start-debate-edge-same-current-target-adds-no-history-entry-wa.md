---
{
  "kind": "edge",
  "routes": {
    "route": "WA Same current target adds no history entry"
  },
  "steps": [
    {
      "text": "Start debate request: Same current target adds no history entry.",
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
      "text": "Selecting the already-current target adds no new history entry.",
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

# Start debate — Same current target adds no history entry — WA

## Trigger

Start debate request: Same current target adds no history entry.

## Outcome

Selecting the already-current target adds no new history entry.
