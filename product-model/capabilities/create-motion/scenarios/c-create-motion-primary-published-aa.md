---
{
  "kind": "primary",
  "routes": {
    "route": "AA Published"
  },
  "steps": [
    {
      "text": "Create selected item request: Published.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "The Motion type's supporter mode is initiator only, supporters named by the initiator or no initiator, or the Motion, not initiated by a person or already supported enough, needs no collection; and the Motion type does not screen Motions.",
      "kind": "condition",
      "actor": "user",
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
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "API creation saves the Motion and its sections/initiators in Screened; the submitted Motion is published.",
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
          "to": "Screened"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php#setInitialCreated"
    }
  ]
}
---

# Create motion — Published — AA

## Trigger

Create motion request: Published.

## Outcome

API creation saves the Motion and its sections/initiators in Screened; the submitted Motion is published.
