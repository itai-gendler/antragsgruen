---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative deactivation"
  },
  "steps": [
    {
      "text": "Delete account request: Administrative deactivation.",
      "kind": "actor",
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-account-administration"
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-account-administration"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php#actionSave"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php#deleteUser"
    }
  ]
}
---

# Delete account — Administrative deactivation — WA

## Trigger

Delete account request: Administrative deactivation.

## Outcome

Deactivation/anonymization cleans applicable memberships/requests, while some historical names remain.
