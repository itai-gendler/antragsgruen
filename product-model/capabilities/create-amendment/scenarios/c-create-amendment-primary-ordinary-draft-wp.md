---
{
  "kind": "primary",
  "routes": {
    "route": "WP Ordinary draft"
  },
  "steps": [
    {
      "text": "Create amendment request: Ordinary draft.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      }
    },
    {
      "text": "An Amendment Draft is saved against the base Motion text; the actor reaches confirmation.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "creates",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Public tags",
            "Procedure tags"
          ],
          "to": "Draft"
        },
        {
          "entity": "amendment-text-section",
          "effect": "creates",
          "facts": [
            "Section identity",
            "Language",
            "Proposed content",
            "Baseline"
          ],
          "with": "amendment"
        },
        {
          "entity": "supporter",
          "effect": "creates",
          "facts": [
            "Target",
            "Role",
            "Identity",
            "Person information",
            "Organization",
            "Contact",
            "Order",
            "Gender",
            "Publicity",
            "Resolution date"
          ],
          "with": "amendment"
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Text",
            "Disposition"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Permissions.php"
    }
  ]
}
---

# Create amendment — Ordinary draft — WP

## Trigger

Create amendment request: Ordinary draft.

## Outcome

An Amendment Draft is saved against the base Motion text; the actor reaches confirmation.
