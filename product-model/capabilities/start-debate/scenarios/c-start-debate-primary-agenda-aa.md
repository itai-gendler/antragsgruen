---
{
  "kind": "primary",
  "routes": {
    "route": "AA Agenda"
  },
  "steps": [
    {
      "text": "Start debate request: Agenda.",
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
          "place": "antragsgruen-api::authenticated"
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

# Start debate — Agenda — AA

## Trigger

Start debate request: Agenda.

## Outcome

The selected Agenda becomes the current Debate target; a different prior Debate is ended.
