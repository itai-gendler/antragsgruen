---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "start-speech",
      "contexts": [
        {
          "place": "web::authenticated"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "assign-speaking-slot",
      "contexts": [
        {
          "place": "web::authenticated"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "unassign-speaking-slot",
      "contexts": [
        {
          "place": "web::authenticated"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/SpeechController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    }
  ]
}
---

# Speech start stops another ongoing speech.

Starting the selected speech stops another ongoing entry. Slot assignment/unassignment resets applicable start/stop dates; waiting/application ordering is distinct from positive assigned slot ordering.
