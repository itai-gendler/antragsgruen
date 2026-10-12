---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion administrative text edit"
  },
  "steps": [
    {
      "text": "Edit record request: Motion administrative text edit.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration"
        }
      }
    },
    {
      "text": "The Motion text is saved through the administrative form.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Title",
            "Text"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "changes",
          "facts": [
            "Content"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration"
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

# Edit document — Motion administrative text edit — WA

## Trigger

Edit document request: Motion administrative text edit.

## Outcome

The Motion text is saved through the administrative form.
