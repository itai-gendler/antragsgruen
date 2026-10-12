---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove personal factor"
  },
  "steps": [
    {
      "text": "Disable second factor request: Remove personal factor.",
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
      "text": "The supplied code matches an enrolled factor key. That matching key is removed from the personal configuration and any other enrolled keys remain.",
      "kind": "product",
      "actor": "user",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/SecondFactorAuthentication.php#attemptRemovingSecondFactor"
    }
  ]
}
---

# Disable second factor — Remove personal factor — WA

## Trigger

Disable second factor request: Remove personal factor.

## Outcome

The supplied code matches an enrolled factor key. That matching key is removed from the personal configuration and any other enrolled keys remain.
