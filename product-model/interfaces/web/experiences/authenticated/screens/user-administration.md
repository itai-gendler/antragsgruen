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
      "entity": "access-request",
      "shows": [
        "Account",
        "Consultation",
        "Request information"
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
    },
    {
      "entity": "organization",
      "shows": [
        "Name",
        "Automatic groups"
      ]
    },
    {
      "entity": "membership",
      "shows": [
        "Account",
        "Group",
        "Container"
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
      "target": "controllers/admin/UsersController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationUserGroup.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Consultation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    }
  ]
}
---

# User administration

Consultation account/request/group catalogue and organization entries.
