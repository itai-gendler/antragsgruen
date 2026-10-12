---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment submitted-initiator edit"
  },
  "steps": [
    {
      "text": "Edit record request: Amendment submitted-initiator edit.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-text-section",
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
      "text": "The Amendment text is saved through the submitted-initiator form.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Changes",
            "Reason"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "changes",
          "facts": [
            "Proposed content"
          ]
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

# Edit document — Amendment submitted-initiator edit — WA

## Trigger

Edit document request: Amendment submitted-initiator edit.

## Outcome

The Amendment text is saved through the submitted-initiator form.
