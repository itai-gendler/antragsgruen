---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::consultation"
        },
        {
          "place": "web::public::consultation"
        }
      ],
      "facts": [
        "Participation settings"
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
      "target": "models/db/Consultation.php"
    }
  ]
}
---

# Consultation web consultation is available to the applicable readers

Web requests preserve maintenance handling (home presents its maintenance outcome), unrestricted CONSULTATION_SETTINGS exception, forced-login checks and consultation-password proof. Managed membership and allowed auth methods are checked only inside forceLogin; SITE_ADMIN is the inspected protected-page override.
