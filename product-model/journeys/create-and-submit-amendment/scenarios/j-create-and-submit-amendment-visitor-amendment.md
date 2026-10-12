---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "Visitor Amendment"
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
      },
      "capability": "create-amendment"
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
      },
      "capability": "create-amendment"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      },
      "capability": "create-amendment"
    },
    {
      "text": "Submit amendment request: Unscreened.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      },
      "capability": "submit-amendment"
    },
    {
      "text": "Confirmation saves the Amendment in Unscreened with submission information, awaiting screening.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Disposition",
            "Submission information"
          ],
          "from": "Draft",
          "to": "Unscreened"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      },
      "capability": "submit-amendment"
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

# Create and submit Amendment — Visitor — Amendment

## Trigger

Prepare and submit the new Amendment.

## Outcome

The saved draft has entered its configured submission lifecycle.
