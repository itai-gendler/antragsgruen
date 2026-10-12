---
{
  "kind": "primary",
  "routes": {
    "route": "AA Attach existing Voting"
  },
  "steps": [
    {
      "text": "Attach debate selected item request: Attach existing selected item.",
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
      "text": "Existing selected ballot attaches to current debate.",
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

# Attach debate voting — Attach existing Voting — AA

## Trigger

Attach debate voting request: Attach existing Voting.

## Outcome

Existing selected ballot attaches to current debate.
