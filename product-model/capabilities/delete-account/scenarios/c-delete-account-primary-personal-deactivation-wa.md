---
{
  "kind": "primary",
  "routes": {
    "route": "WA Personal deactivation"
  },
  "steps": [
    {
      "text": "Delete account request: Personal deactivation.",
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
      "text": "Deactivation/anonymization cleans applicable memberships/requests, while some historical names remain.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Name",
            "Email",
            "Authentication identity",
            "Account restrictions",
            "Organization",
            "Email confirmation",
            "Password configuration"
          ],
          "to": "Deactivated",
          "from": "Confirmed"
        },
        {
          "entity": "membership",
          "effect": "removes"
        },
        {
          "entity": "access-request",
          "effect": "removes"
        },
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Session context"
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
      "target": "models/db/User.php#deleteAccount"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionMyaccount"
    }
  ]
}
---

# Delete account — Personal deactivation — WA

## Trigger

Delete account request: Personal deactivation.

## Outcome

Deactivation/anonymization cleans applicable memberships/requests, while some historical names remain.
