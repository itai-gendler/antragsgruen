---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Disposition",
        "Address"
      ],
      "contexts": [
        {
          "place": "web::authenticated::incorporate-amendment"
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
    }
  ]
}
---

# Motion replace incorporation is available to the configured participants

Incorporation refuses amendments-only/statutes mode. Unrestricted CONTENT_EDIT or the source Motion’s identified initiator with the configured merge setting may proceed. The no-collision initiator setting uses detected collisions with its actual override behavior. Other-Amendment disposition edits retain the staff CONTENT_EDIT branch.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
