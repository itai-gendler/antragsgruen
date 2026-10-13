---
{
  "kind": "primary",
  "routes": {
    "route": "AP Unscreened"
  },
  "steps": [
    {
      "text": "Create selected item request: Unscreened.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "The Motion type's supporter mode is initiator only, supporters named by the initiator or no initiator, or the Motion, not initiated by a person or already supported enough, needs no collection; and the Motion type screens Motions.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Initiators"
          ]
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Role",
            "Gender"
          ]
        },
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": [
            "Supporter mode",
            "Support thresholds",
            "Screening"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "API creation saves the Motion and its sections/initiators in Unscreened, awaiting screening.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "antragsgruen-api::public"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php#setInitialCreated"
    }
  ]
}
---

# Create motion — Unscreened — AP

## Trigger

Create motion request: Unscreened.

## Outcome

API creation saves the Motion and its sections/initiators in Unscreened, awaiting screening.
