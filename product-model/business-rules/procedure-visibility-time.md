---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "publish-proposed-procedure",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "unpublish-proposed-procedure",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "read-proposed-procedure",
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
    }
  ],
  "references": [
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/ConsultationController.php"
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
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Publication uses and preserves its kept visibility time.

The kept visible-from time determines whether a version is public. Unpublication clears it. Publication retains its actual existing/time-selection behavior rather than inventing a new version or equating publication with document disposition.
