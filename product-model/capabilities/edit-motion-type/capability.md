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
      "target": "controllers/rest/MotionTypeController.php#actionUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/motionType/MotionTypeUpdateRequest.php"
    }
  ],
  "domain": "motion-types"
}
---

# Edit motion type

Type metadata/settings persist; Web section definitions remain independently editable, without API parity.
