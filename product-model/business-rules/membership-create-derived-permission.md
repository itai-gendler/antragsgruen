---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "membership",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::user-administration"
        },
        {
          "place": "web::authenticated::user-group-administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php#containsPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php#hasPrivilege"
    }
  ]
}
---

# Membership create derived is available to the configured administrators

Ordinary administration requires unrestricted CONSULTATION_SETTINGS with actual selectable-group/site checks and protection against administrative self-lockout. Import requires CONSULTATION_SETTINGS but directly changes membership links without repeating all ordinary site/selectability/self-removal checks. Derived approval/default-group/account-lifecycle links follow their actual parent authority. Voting participant-group addition/removal requires VOTINGS and its group/site/self checks, not an inferred CONSULTATION_SETTINGS prerequisite.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
