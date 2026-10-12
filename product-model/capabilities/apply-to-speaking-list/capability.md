---
{
  "availability": [
    {
      "place": "web::public"
    },
    {
      "place": "web::authenticated"
    },
    {
      "place": "antragsgruen-api::public"
    },
    {
      "place": "antragsgruen-api::authenticated"
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
  ],
  "domain": "speaking-lists"
}
---

# Apply to speaking list

Ordinary or point-of-order application persists with account/cookie identity, configured name and selected subqueue.
