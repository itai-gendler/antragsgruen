---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-motion",
      "contexts": [
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
      ]
    },
    {
      "type": "capability",
      "id": "create-amendment",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Permissions.php"
    }
  ]
}
---

# Creation keeps its implemented draft/submission outcome.

Web creation saves a persistent Draft and requires confirmation. API Motion creation applies its configured collecting, unscreened or screened outcome immediately; there is no mapped core API Amendment-create parity.
