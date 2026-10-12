---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove item/group"
  },
  "steps": [
    {
      "text": "Remove voting item request: Remove item/group.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting-question",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-administration"
        }
      }
    },
    {
      "text": "Selected record assignment or question/group is removed from the ballot.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting-question",
          "effect": "removes"
        },
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Voting information"
          ]
        },
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Voting information"
          ]
        },
        {
          "entity": "voting",
          "effect": "changes",
          "facts": [
            "Assignments"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::voting-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/VotingController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/VotingMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/voting/VotingPayloadBuilder.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/VotingController.php"
    }
  ]
}
---

# Remove voting item — Remove item/group — WA

## Trigger

Remove voting item request: Remove item/group.

## Outcome

Selected document assignment or question/group is removed from the ballot.
