---
{
  "kind": "primary",
  "routes": {
    "route": "AA Create/attach Voting"
  },
  "steps": [
    {
      "text": "Create selected item selected item request: Create/attach selected item.",
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
      "text": "A ballot is created and attached through debate moderation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "creates",
          "facts": [
            "Title",
            "Phase",
            "Order",
            "Assignments",
            "Answers",
            "Majority and quorum",
            "Participation policy",
            "Limits",
            "Publicity",
            "Opening snapshot"
          ]
        },
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

# Create debate voting — Create/attach Voting — AA

## Trigger

Create debate voting request: Create/attach Voting.

## Outcome

A ballot is created and attached through debate moderation.
