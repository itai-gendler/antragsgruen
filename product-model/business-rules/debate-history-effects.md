---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "start-debate",
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
      "id": "end-debate",
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
      "id": "delete-agenda-item",
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
      "id": "delete-document",
      "contexts": [
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
      "target": "controllers/rest/DebateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/DebateTools.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/IndexController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
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

# Debate replacement, document invisibility and agenda deletion have distinct history effects.

Selecting an already-current target is idempotent. Selecting a different target ends the prior entry. Document invisibility ends current debate while retaining history; deleting an agenda item deletes its associated debate history.
