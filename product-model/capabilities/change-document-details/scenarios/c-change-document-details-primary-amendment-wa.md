---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Change record details request: Amendment.",
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
          "place": "web::authenticated::amendment-administration"
        }
      }
    },
    {
      "text": "Administrative Save writes details, disposition, numbering, flags, dates, internal note and associations; posted disposition is assigned directly.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Title",
            "Disposition",
            "Submission information",
            "Flags",
            "Internal note",
            "Base"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-administration"
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

# Change document details — Amendment — WA

## Trigger

Change document details request: Amendment.

## Outcome

Administrative Save writes details, disposition, numbering, flags, dates, internal note and associations; posted disposition is assigned directly.
