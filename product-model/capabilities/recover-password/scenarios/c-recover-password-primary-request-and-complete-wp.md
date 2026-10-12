---
{
  "kind": "primary",
  "routes": {
    "route": "WP Request and complete"
  },
  "steps": [
    {
      "text": "Recover password request: Request and complete.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-recovery"
        }
      }
    },
    {
      "text": "The Product reads the recovery destination and sends its recovery link.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email",
            "Password configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-recovery"
        }
      }
    },
    {
      "text": "The requested recovery link is mailed to the saved account address. Following the matching token and entering a valid new password stores the password for that resolved account; this process does not establish a Web session.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-recovery"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionRecovery"
    }
  ]
}
---

# Recover password — Request and complete — WP

## Trigger

Recover password request: Request and complete.

## Outcome

The requested recovery link is mailed to the saved account address. Following the matching token and entering a valid new password stores the password for that resolved account; this process does not establish a Web session.
