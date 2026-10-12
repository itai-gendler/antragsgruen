---
{
  "kind": "primary",
  "routes": {
    "route": "WA CSV processing with skip/merge/replace"
  },
  "steps": [
    {
      "text": "Supply the CSV file, collision choice and welcome-message choice.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-import"
        }
      }
    },
    {
      "text": "The Product persists the new account row and its selected group memberships.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
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
          ],
          "to": "Confirmed",
          "as": "new"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ],
          "as": "new-membership",
          "with": "new"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-import"
        }
      }
    },
    {
      "text": "The Product applies the chosen merge/replace behavior to the existing account row, updating supplied name/affiliation and direct group links.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Name",
            "Organization"
          ],
          "as": "existing"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ],
          "as": "existing-membership"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-import"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php"
    }
  ]
}
---

# Import consultation users — CSV processing with skip/merge/replace — WA

## Trigger

A valid CSV chunk includes new and existing accounts; the concrete existing-row example selects Merge. The chosen collision policy governs other runs.

## Outcome

CSV chunks apply skip/merge/replace collisions; existing profile and direct membership effects follow import-specific guards.

## Decision points

### Existing email collision

Which collision behavior was selected?

- Skip → Existing rows are skipped and contribute no profile or membership change.
- Merge → Supplied profile values update and missing group links are added.
- Replace → Supplied profile values update; applicable old consultation memberships are removed and supplied links are added.
