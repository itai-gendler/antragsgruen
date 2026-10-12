---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Disposition"
      ],
      "contexts": [
        {
          "place": "web::authenticated::motion"
        }
      ],
      "to": "Withdrawn"
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
      "target": "models/db/Motion.php"
    }
  ]
}
---

# Motion withdraw is available to the owner

Only the identified initiator withdraws collecting, unscreened or screened submitted contents. Ordinary withdrawal does not admit Draft; its otherwise present draft-deletion implementation is not a reachable general grant.
