---
{
  "kind": "validation",
  "routes": {
    "route": "WA Request refused"
  },
  "steps": [
    {
      "text": "Read speaking-list administration request: Request refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    },
    {
      "text": "The speaking administration request check stops this request. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/ConsultationController.php"
    },
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
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/SpeechController.php"
    }
  ]
}
---

# Read speaking-list administration — Request refused — WA

## Trigger

Read speaking-list administration request: Request refused.

## Outcome

The speaking administration request check stops this request. This attempt does not complete the requested operation.
