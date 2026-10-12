---
{
  "kind": "primary",
  "routes": {
    "route": "WA Published"
  },
  "steps": [
    {
      "text": "Submit amendment request: Published.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      }
    },
    {
      "text": "Confirmation saves the Amendment in Screened with submission/publication information.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Disposition",
            "Submission information"
          ],
          "from": "Draft",
          "to": "Screened"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
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

# Submit amendment — Published — WA

## Trigger

Submit amendment request: Published.

## Outcome

Confirmation saves the Amendment in Screened with submission/publication information.
