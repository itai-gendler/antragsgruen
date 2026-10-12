---
{
  "kind": "edge",
  "routes": {
    "route": "WP Child deadline checks differ"
  },
  "steps": [
    {
      "text": "Submit amendment request: Child deadline checks differ.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      }
    },
    {
      "text": "Child creation/editing checks the child deadline; confirmation checks the ordinary amendment deadline.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      }
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

# Submit amendment — Child deadline checks differ — WP

## Trigger

Submit amendment request: Child deadline checks differ.

## Outcome

Child creation/editing checks the child deadline; confirmation checks the ordinary amendment deadline.
