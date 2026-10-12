---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "procedure-note",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::procedure-administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IAdminComment.php"
    }
  ]
}
---

# Procedure note remove is available to the owner

The note author removes their own procedure note after actual document access; the removal branch adds no separate staff-privilege check.
