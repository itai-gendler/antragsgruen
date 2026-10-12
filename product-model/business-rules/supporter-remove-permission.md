---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "supporter",
      "effect": "removes",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::amendment"
        },
        {
          "place": "web::public::motion"
        },
        {
          "place": "web::public::amendment"
        },
        {
          "place": "web::authenticated::motion"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    },
    {
      "configuredBy": "consultation"
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ISupporter.php"
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

# Supporter remove is available to the owner and configured administrators

Own official support revocation uses signed account or retained anonymous cookie continuity; reaction replacement removes that identity’s prior participation through its support operation. Administrative participation removal retains its actual initiator-edit authority.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
