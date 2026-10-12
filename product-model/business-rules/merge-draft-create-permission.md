---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "merge-draft",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
    },
    {
      "configuredBy": "motion-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Draft.php"
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

# Merge draft create is available to the configured participants

Assembly needs no non-draft successor and the MERGING deadline, then scoped MOTION_STATUS_EDIT or the source Motion’s identified initiator under configured merge authority. Its no-collision initiator setting actually requires zero visible Amendments. Resolution creation additionally requires scoped MOTION_STATUS_EDIT. Public reading requires a saved Public draft and applicable consultation access; working/PDF access uses assembly authority, not unrestricted public draft visibility.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
