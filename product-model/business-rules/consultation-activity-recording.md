---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "submit-motion",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "submit-amendment",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "screen-document",
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
      "id": "unscreen-document",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "withdraw-document",
      "contexts": [
        {
          "place": "web::authenticated"
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
    },
    {
      "type": "capability",
      "id": "edit-proposed-procedure",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "assign-document-voting",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "entity",
      "id": "activity-entry"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IProposal.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/ProposedProcedureController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/ProposedChangeForm.php"
    }
  ]
}
---

# Inspected consultation operations record their actual activity.

The traced creation/submission, screening, withdrawal/deletion, procedure and assignment operations record their actual disclosed consultation activity. This asserts only the inspected source log calls; it is not a universal record-every-mutation guarantee.
