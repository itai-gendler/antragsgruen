---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-document",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MotionEditForm.php#updateTextRewritingAmendments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MotionEditForm.php#saveMotion"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionController.php#actionGetAmendmentRewriteCollisions"
    }
  ]
}
---

# Administrative Motion rewriting checks unresolved dependent inconsistency.

The form checks all relevant dependent Amendment sections before applying their rewrites and considers supplied overrides. An unresolved canRewrite result returns false before rewriting these sections. saveMotion does not propagate that boolean as a FormError: ordinary valid detail saves and earlier effects can persist, with no transaction rollback or general save-refusal guarantee. The separate collision-preview endpoint presents the detected conflicts.
