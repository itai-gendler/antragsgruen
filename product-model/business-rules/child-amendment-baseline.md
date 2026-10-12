---
{
  "appliesTo": [
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

# Child Amendments retain their baseline and stop before a third level.

Ordinary amendments use the Motion baseline; children use their parent Amendment baseline. Third-level creation is refused. Child creation/editing checks its child deadline while confirmation rechecks the ordinary amendment policy/deadline.
