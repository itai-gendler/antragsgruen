---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Account"
  },
  "steps": [
    {
      "text": "Sign in request: Password-change hand-off.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "Credential verification retains the pending Account and carries the actor to required password change.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Pending authentication"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Authentication identity",
            "Email confirmation",
            "Password configuration",
            "Second-factor configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "Change password request: Forced.",
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
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "change-password"
    },
    {
      "text": "A matching new password is stored; forced change completes the pending target continuation.",
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
          "place": "web::authenticated::sign-in"
        }
      },
      "capability": "change-password"
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

# Complete sign-in with required password change — User — Account

## Trigger

Complete required password change while signing in.

## Outcome

The pending target has the new password and completes authentication.
