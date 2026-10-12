---
{
  "kind": "primary",
  "routes": {
    "route": "AA Token"
  },
  "steps": [
    {
      "text": "Sign in request: Token.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "API credential verification returns a signed authentication token and expiry for the resolved Account; it establishes no Web session or pending interactive challenge.",
      "kind": "product",
      "actor": "user",
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
          "place": "antragsgruen-api::authenticated"
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

# Sign in — Token — AA

## Trigger

Sign in request: Token.

## Outcome

API credential verification returns a signed authentication token and expiry for the resolved Account; it establishes no Web session or pending interactive challenge.
