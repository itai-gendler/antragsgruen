---
{
  "entities": [
    {
      "entity": "voting",
      "shows": [
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
      "shows": [
        "Text",
        "Voting association",
        "Result information",
        "Abstention"
      ]
    },
    {
      "entity": "motion",
      "shows": [
        "Title",
        "Address",
        "Text",
        "Initiators",
        "Disposition",
        "Submission information",
        "Flags",
        "Protocol",
        "Responsibility",
        "Voting information",
        "Internal note",
        "Relationships"
      ]
    },
    {
      "entity": "amendment",
      "shows": [
        "Base",
        "Title",
        "Changes",
        "Reason",
        "Alternative information",
        "Initiators",
        "Disposition",
        "Submission information",
        "Flags",
        "Responsibility",
        "Voting information",
        "Internal note"
      ]
    },
    {
      "entity": "vote",
      "shows": [
        "Account",
        "Voting and item",
        "Answer",
        "Weight",
        "Time",
        "Retained publicity"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingQuestion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Amendment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Vote.php"
    }
  ]
}
---

# Voting results

Permitted closed results and individual-vote information under retained/current publicity.
