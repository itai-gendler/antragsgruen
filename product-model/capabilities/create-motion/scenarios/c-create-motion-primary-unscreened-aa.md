---
{
  "kind": "primary",
  "routes": {
    "route": "AA Unscreened"
  },
  "steps": [
    {
      "text": "Create motion request: Unscreened.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
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
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "API creation saves the Motion and its sections/initiators in Unscreened, awaiting screening.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "creates",
          "facts": [
            "Title",
            "Address",
            "Text",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Protocol",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Relationships",
            "Public tags",
            "Procedure tags"
          ],
          "to": "Unscreened"
        },
        {
          "entity": "motion-text-section",
          "effect": "creates",
          "facts": [
            "Section identity",
            "Language",
            "Content",
            "Activity",
            "Publicity"
          ],
          "with": "motion"
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
          "with": "motion"
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
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

# Create motion — Unscreened — AA

## Trigger

Create motion request: Unscreened.

## Outcome

API creation saves the Motion and its sections/initiators in Unscreened, awaiting screening.
