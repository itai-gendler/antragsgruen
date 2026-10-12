---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "activity-entry",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::consultation"
        },
        {
          "place": "web::authenticated::consultation"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "consultation"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationLog.php"
    }
  ]
}
---

# Activity entry read is available to the applicable readers

Consultation activity follows actual consultation access and the log projection’s disclosed operation, actor, subject and details.
