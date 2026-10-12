---
{
  "availability": [
    {
      "place": "web::authenticated"
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

# Reset speaking list

The list's entries are removed.
