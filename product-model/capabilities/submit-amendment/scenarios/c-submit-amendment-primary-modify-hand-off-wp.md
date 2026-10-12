---
{
  "kind": "primary",
  "routes": {
    "route": "WP Modify hand-off"
  },
  "steps": [
    {
      "text": "Submit amendment request: Modify hand-off.",
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
      "text": "Modify returns the actor to the saved Amendment editor; the Draft is not submitted.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Responsibility",
            "Voting information",
            "Internal note"
          ]
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

# Submit amendment — Modify hand-off — WP

## Trigger

Submit amendment request: Modify hand-off.

## Outcome

Modify returns the actor to the saved Amendment editor; the Draft is not submitted.
