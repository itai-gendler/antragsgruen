---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment published"
  },
  "steps": [
    {
      "text": "Finish supporter collection request: Amendment published.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment"
        }
      }
    },
    {
      "text": "Explicit completion moves the collecting Amendment to Screened and published and records submission information.",
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
          "from": "Collecting",
          "to": "Screened"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment"
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

# Finish supporter collection — Amendment published — WA

## Trigger

Finish supporter collection request: Amendment published.

## Outcome

Explicit completion moves the collecting Amendment to Screened and published and records submission information.
