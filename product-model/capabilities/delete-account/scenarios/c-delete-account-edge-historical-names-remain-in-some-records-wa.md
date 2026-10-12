---
{
  "kind": "edge",
  "routes": {
    "route": "WA Historical names remain in some records"
  },
  "steps": [
    {
      "text": "Delete account request: Historical names remain in some records.",
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
    },
    {
      "text": "Historical initiator/supporter/record names can remain after anonymization/deactivation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "membership",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
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

# Delete account — Historical names remain in some records — WA

## Trigger

Delete account request: Historical names remain in some records.

## Outcome

Historical initiator/supporter/document names can remain after anonymization/deactivation.
