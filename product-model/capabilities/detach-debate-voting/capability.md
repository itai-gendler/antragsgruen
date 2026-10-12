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

# Detach debate voting

The current debate's ballot attachment is removed.
