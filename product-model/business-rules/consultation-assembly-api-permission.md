---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "reads",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "antragsgruen-api::public"
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

# Consultation assembly api is available to the applicable readers

Base access applies to every mapped API request. Assembly alwaysEnabled skips the handler’s extra API switch/maintenance check, while earlier Base consultation access still applies. Forced-login membership/auth-method conditions and anonymous consultation-password proof remain as implemented.
