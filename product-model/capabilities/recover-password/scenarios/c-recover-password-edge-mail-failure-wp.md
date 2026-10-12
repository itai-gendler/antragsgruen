---
{
  "kind": "edge",
  "routes": {
    "route": "WP Mail failure"
  },
  "steps": [
    {
      "text": "Recover password request: Mail failure.",
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
      "text": "The Product reads the saved recovery destination for the attempted mail.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email"
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
      "text": "Recovery mail fails after the new recovery proof and request time have been saved. The error is shown without establishing receipt, a changed password or a Web session.",
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
      "target": "models/db/User.php#sendRecoveryMail"
    }
  ]
}
---

# Recover password — Mail failure — WP

## Trigger

Recover password request: Mail failure.

## Outcome

Recovery mail fails after the new recovery proof and request time have been saved. The error is shown without establishing receipt, a changed password or a Web session.
