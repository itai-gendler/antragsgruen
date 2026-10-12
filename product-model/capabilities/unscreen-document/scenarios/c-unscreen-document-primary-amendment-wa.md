---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Unscreen record request: Amendment.",
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
          "place": "web::authenticated::motion-administration-list"
        }
      }
    },
    {
      "text": "The list operation returns the selected record to unscreened disposition.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Disposition"
          ],
          "from": "Screened",
          "to": "Unscreened"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration-list"
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

# Unscreen document — Amendment — WA

## Trigger

Unscreen document request: Amendment.

## Outcome

The list operation returns the selected document to unscreened disposition.
