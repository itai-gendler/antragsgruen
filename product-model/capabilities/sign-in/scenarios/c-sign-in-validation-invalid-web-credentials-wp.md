---
{
  "kind": "validation",
  "routes": {
    "route": "WP Invalid Web credentials"
  },
  "steps": [
    {
      "text": "Sign in request: Invalid Web credentials.",
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
          "place": "web::public::sign-in"
        }
      }
    },
    {
      "text": "Invalid Web credentials leave the sign-in process incomplete and present the login error.",
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
          "place": "web::public::sign-in"
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

# Sign in — Invalid Web credentials — WP

## Trigger

Sign in request: Invalid Web credentials.

## Outcome

Invalid Web credentials leave the sign-in process incomplete and present the login error.
