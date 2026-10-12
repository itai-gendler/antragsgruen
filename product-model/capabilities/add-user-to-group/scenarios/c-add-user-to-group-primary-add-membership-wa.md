---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add Membership"
  },
  "steps": [
    {
      "text": "Add user to group request: Add Membership.",
      "kind": "actor",
      "actor": "user",
      "entities": [
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
      "text": "Applicable selectable-group membership is added with actual site checks.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ]
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
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

# Add user to group — Add Membership — WA

## Trigger

Add user to group request: Add Membership.

## Outcome

Applicable selectable-group membership is added with actual site checks.
