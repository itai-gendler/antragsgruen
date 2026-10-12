---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add/create Account and memberships"
  },
  "steps": [
    {
      "text": "Add selected item user request: Add/create Account and memberships.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [],
          "as": "new"
        },
        {
          "entity": "membership",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
        }
      }
    },
    {
      "text": "Selected/new account and memberships persist; welcome mail follows persistence.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Name",
            "Email",
            "Organization",
            "Authentication identity",
            "Email confirmation",
            "Password configuration",
            "Second-factor configuration",
            "Account restrictions",
            "Vote weights",
            "Pending email change",
            "Preferred language"
          ],
          "to": "Confirmed",
          "as": "new"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ],
          "with": "new"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php"
    }
  ]
}
---

# Add consultation user — Add/create Account and memberships — WA

## Trigger

Add consultation user request: Add/create Account and memberships.

## Outcome

Selected/new account and memberships persist; welcome mail follows persistence.
