---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "Visitor Account"
  },
  "steps": [
    {
      "text": "Sign in request: Second-factor hand-off.",
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
      "text": "Credential verification retains the pending Account and factor challenge, then carries the actor to second-factor verification.",
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
      "text": "Verify second factor request: Complete pending authentication.",
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
      "capability": "verify-second-factor"
    },
    {
      "text": "The pending target's factor proof completes its pending authentication.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "changes",
          "facts": [
            "Pending authentication"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "verify-second-factor"
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

# Complete sign-in with second factor — Visitor — Account

## Trigger

Complete the pending factor challenge.

## Outcome

Authentication for the pending target completes.
