---
{
  "kind": "primary",
  "routes": {
    "route": "WA Repeat request and complete"
  },
  "steps": [
    {
      "text": "Recover password request: Repeat request and complete.",
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
          "place": "web::authenticated::password-recovery"
        }
      }
    },
    {
      "text": "The Product reads the recovery destination and sends its recovery link.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::password-recovery"
        }
      }
    },
    {
      "text": "A repeated recovery request renews and sends the saved account’s recovery link. Following the matching token and entering a valid new password stores the password for that resolved account; this process does not establish a Web session.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::password-recovery"
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

# Recover password — Repeat request and complete — WA

## Trigger

Recover password request: Repeat request and complete.

## Outcome

A repeated recovery request renews and sends the saved account’s recovery link. Following the matching token and entering a valid new password stores the password for that resolved account; this process does not establish a Web session.
