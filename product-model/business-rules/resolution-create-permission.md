---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "resolution",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::merge-amendments"
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
      "target": "models/mergeAmendments/Merge.php"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php#canCreateResolution"
    }
  ]
}
---

# Resolution create is available to the configured administrators

Assembly needs no non-draft successor and the MERGING deadline, then scoped MOTION_STATUS_EDIT or the source Motion’s identified initiator under configured merge authority. Its no-collision initiator setting actually requires zero visible Amendments. Resolution creation additionally requires MOTION_STATUS_EDIT evaluated against the newly created preview Motion’s own context, through its canCreateResolution check; a privilege on the source alone does not replace that check.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
