---
{
  "kind": "primary",
  "routes": {
    "route": "WP Motion draft"
  },
  "steps": [
    {
      "text": "Edit record request: Motion draft.",
      "kind": "actor",
      "actor": "visitor",
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
          "place": "web::public::motion-submission"
        }
      }
    },
    {
      "text": "The Motion text is saved through the Draft editor; the actor returns to submission confirmation.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "web::public::motion-submission"
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

# Edit document — Motion draft — WP

## Trigger

Edit document request: Motion draft.

## Outcome

The Motion text is saved through the Draft editor; the actor returns to submission confirmation.
