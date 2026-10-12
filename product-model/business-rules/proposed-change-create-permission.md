---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "proposed-change",
      "effect": "creates"
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
      "target": "models/forms/ProposedChangeForm.php"
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

# Proposed change create is available to the configured administrators

Alternative writing/removal uses Full procedure: scoped CHANGE_PROPOSALS or unrestricted CONSULTATION_SETTINGS, plus public-edit setting or consultation-settings override when already public. Actual published/requested-feedback/staff branches govern alternative disclosure. Amendment inherited alternatives follow recursive move/supersession references up to the implemented nesting limit, not an invented stored inheritance fact.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
