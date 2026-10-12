---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Disposition",
        "Submission information"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment"
        }
      ],
      "from": "Collecting"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "supporter"
        },
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ],
      "when": [
        {
          "entity": "supporter",
          "fact": "Role",
          "is": "Initiator"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Amendment.php"
    }
  ]
}
---

# Amendment finish collection is available to the owner

An identified initiator finishes only a collecting document that passes deadline and ordinary/female support thresholds.
