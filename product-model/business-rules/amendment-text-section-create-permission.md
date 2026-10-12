---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-text-section",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::amendment-submission"
        },
        {
          "place": "web::public::amendment-submission"
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
      "target": "models/db/AmendmentSection.php"
    }
  ]
}
---

# Amendment text section create is available to the configured participants

Text-section creation follows the containing document creation; section requirements and content languages come from its addressed definition.
