---
{
  "kind": "primary",
  "routes": {
    "route": "AP Token"
  },
  "steps": [
    {
      "text": "Sign in request: Token.",
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
      "text": "API credential verification returns a signed authentication token and expiry for the resolved Account; it establishes no Web session or pending interactive challenge.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Authentication identity",
            "Account restrictions",
            "Email confirmation",
            "Second-factor configuration"
          ]
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/UserController.php#actionLogin"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/user/UserLoginResponse.php#fromLogin"
    }
  ]
}
---

# Sign in — Token — AP

## Trigger

Sign in request: Token.

## Outcome

API credential verification returns a signed authentication token and expiry for the resolved Account; it establishes no Web session or pending interactive challenge.
