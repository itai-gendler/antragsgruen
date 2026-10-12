---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "procedure-note",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::procedure-administration"
        },
        {
          "place": "web::authenticated::motion"
        },
        {
          "place": "web::authenticated::amendment"
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
      "target": "models/db/IAdminComment.php"
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
      "target": "views/motion/view.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "views/amendment/view.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "views/shared/_proposed_procedure_log.php"
    }
  ]
}
---

# Procedure note read is available to the configured administrators

Staff notes in a Motion or Amendment view require the implemented proposed-procedure feature and Limited-procedure authority: contextual CHANGE_PROPOSALS or unrestricted CONSULTATION_SETTINGS. The Motion widget also excludes Resolutions. Procedure administration and selected internal exports use their actual controller entry checks; public-only projections disclose no staff notes.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
