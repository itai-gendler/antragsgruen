---
{
  "kind": "validation",
  "routes": {
    "route": "AP API interactive prerequisite refused"
  },
  "steps": [
    {
      "text": "Sign in request: API interactive prerequisite refused.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "The API returns a refusal for an interactive prerequisite, without issuing an authentication token.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
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

# Sign in — API interactive prerequisite refused — AP

## Trigger

Sign in request: API interactive prerequisite refused.

## Outcome

The API returns a refusal for an interactive prerequisite, without issuing an authentication token.
