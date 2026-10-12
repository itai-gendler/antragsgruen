---
{
  "entities": [
    {
      "entity": "user-group",
      "shows": [
        "Name",
        "Scope",
        "Template",
        "Selectability",
        "Permissions"
      ]
    },
    {
      "entity": "membership",
      "shows": [
        "Account",
        "Group",
        "Container"
      ]
    },
    {
      "entity": "permission-entry",
      "shows": [
        "Privileges",
        "Tag restriction",
        "Agenda restriction",
        "Type restriction"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationUserGroup.php"
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

# User-group administration

Selected editable group, memberships and scoped permission entries.
