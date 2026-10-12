---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
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
      "entity": "user-group",
      "shows": [
        "Name",
        "Scope",
        "Template",
        "Selectability",
        "Permissions"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationUserGroup.php"
    }
  ]
}
---

# User import

CSV input, collision/mail choices, chunk progress, counts and errors.
