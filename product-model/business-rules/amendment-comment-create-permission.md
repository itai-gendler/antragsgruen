---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-comment",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::amendment"
        },
        {
          "place": "web::public::amendment"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "motion-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentComment.php"
    }
  ]
}
---

# Amendment comment create is available to the configured participants

Comment creation uses the type’s comment policy and actual deadline with no administrative override. Email/token/anti-spam and same-document reply depth are validation.
