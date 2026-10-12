---
{
  "kind": "primary",
  "routes": {
    "route": "WA Create pending request"
  },
  "steps": [
    {
      "text": "Request access request: Create pending request.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-access"
        }
      }
    },
    {
      "text": "A pending consultation request is retained for the requesting account.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "creates",
          "facts": [
            "Account",
            "Consultation",
            "Request information"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-access"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/LoginUsernamePasswordForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/UserController.php"
    }
  ]
}
---

# Request access — Create pending request — WA

## Trigger

Request access request: Create pending request.

## Outcome

A pending consultation request is retained for the requesting account.
