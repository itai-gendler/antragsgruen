---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Disposition",
        "Address",
        "Voting information",
        "Public tags"
      ],
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
    },
    {
      "configuredBy": "motion-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
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
      "target": "models/mergeAmendments/Merge.php#confirm"
    }
  ]
}
---

# Motion replace assembly is available to the configured participants

Assembly needs no non-draft successor and the MERGING deadline, then scoped MOTION_STATUS_EDIT or the source Motion’s identified initiator under configured merge authority. Its no-collision initiator setting actually requires zero visible Amendments. The confirmation also transfers the source Address when a resolution preserves its Disposition. Resolution creation additionally requires MOTION_STATUS_EDIT in the newly created preview’s own context.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
