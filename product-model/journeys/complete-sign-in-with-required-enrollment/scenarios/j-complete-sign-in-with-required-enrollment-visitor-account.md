---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "Visitor Account"
  },
  "steps": [
    {
      "text": "Sign in request: Enrollment hand-off.",
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
      },
      "capability": "sign-in"
    },
    {
      "text": "Credential verification retains the pending Account and carries the actor to required factor enrollment.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
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
          "place": "web::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "Enable second factor request: Forced.",
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
          "place": "web::public::sign-in"
        }
      },
      "capability": "enable-second-factor"
    },
    {
      "text": "Enrollment proof saves factor configuration; required enrollment completes pending authentication.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Second-factor configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "enable-second-factor"
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

# Complete sign-in with required enrollment — Visitor — Account

## Trigger

Complete required factor enrollment while signing in.

## Outcome

The pending target has enrolled and completes authentication.
