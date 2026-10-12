---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-comment",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::public::motion"
        },
        {
          "place": "web::authenticated::motion"
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
      "target": "models/db/MotionComment.php"
    }
  ]
}
---

# Motion comment create is available to the configured participants

Comment creation uses the type’s comment policy and actual deadline with no administrative override. Email/token/anti-spam and same-document reply depth are validation.
