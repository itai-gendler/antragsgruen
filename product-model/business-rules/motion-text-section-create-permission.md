---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-text-section",
      "effect": "creates",
      "contexts": [
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::motion-submission"
        },
        {
          "place": "web::public::motion-submission"
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
      "target": "models/db/MotionSection.php"
    }
  ]
}
---

# Motion text section create is available to the configured participants

Text-section creation follows the containing document creation; section requirements and content languages come from its addressed definition.
