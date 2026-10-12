---
{
  "kind": "primary",
  "routes": {
    "route": "WA Personal profile"
  },
  "steps": [
    {
      "text": "Edit account request: Personal profile.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "Personal name/affiliation or administrative profile/security configuration is saved under its separate field rules.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Name",
            "Organization"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
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

# Edit account — Personal profile — WA

## Trigger

Edit account request: Personal profile.

## Outcome

The personal name and organization changes are saved.
