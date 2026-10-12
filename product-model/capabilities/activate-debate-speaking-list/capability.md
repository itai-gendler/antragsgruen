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
      "target": "controllers/rest/DebateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/DebateTools.php"
    }
  ]
}
---

# Activate debate speaking list

A queue is created or activated and attached to the current debate.
