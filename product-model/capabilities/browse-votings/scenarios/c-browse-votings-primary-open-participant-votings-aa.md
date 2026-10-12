---
{
  "kind": "primary",
  "routes": {
    "route": "AA Open participant votings"
  },
  "steps": [
    {
      "text": "Browse selected item request: Open participant selected item.",
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
      "text": "Open participant ballots, configured items and own voting state are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "reads",
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
          "entity": "voting-question",
          "effect": "reads",
          "facts": [
            "Text",
            "Voting association",
            "Result information",
            "Abstention"
          ]
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": [
            "Account",
            "Voting and item",
            "Answer",
            "Weight",
            "Time",
            "Retained publicity"
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
      "target": "controllers/ConsultationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/VotingController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/voting/VotingPayloadBuilder.php"
    }
  ]
}
---

# Browse votings — Open participant votings — AA

## Trigger

Browse votings request: Open participant votings.

## Outcome

Open participant ballots, configured items and own voting state are returned.
