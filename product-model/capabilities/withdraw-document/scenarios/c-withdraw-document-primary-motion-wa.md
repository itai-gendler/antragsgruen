---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion"
  },
  "steps": [
    {
      "text": "Withdraw record request: Motion.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
        }
      }
    },
    {
      "text": "The identified initiator's collecting/submitted record enters its withdrawn condition.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Disposition"
          ],
          "from": "Screened",
          "to": "Withdrawn"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
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

# Withdraw document — Motion — WA

## Trigger

Withdraw document request: Motion.

## Outcome

The identified initiator's collecting/submitted document enters its withdrawn condition.
