---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Start debate request: Amendment.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
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
      "text": "Visible record, agenda item or nonempty free text becomes current; a different prior debate ends.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "creates",
          "facts": [
            "Target",
            "Start time",
            "End time",
            "Attachments"
          ]
        },
        {
          "entity": "agenda-item",
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

# Start debate — Amendment — WA

## Trigger

Start debate request: Amendment.

## Outcome

The selected Amendment becomes the current Debate target; a different prior Debate is ended.
