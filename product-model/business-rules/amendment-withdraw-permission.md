---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Disposition"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment"
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
      "target": "models/db/Amendment.php"
    }
  ]
}
---

# Amendment withdraw is available to the owner

Only the identified initiator withdraws collecting, unscreened or screened submitted contents. Ordinary withdrawal does not admit Draft; its otherwise present draft-deletion implementation is not a reachable general grant.
