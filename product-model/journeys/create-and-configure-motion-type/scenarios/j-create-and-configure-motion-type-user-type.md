---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Type"
  },
  "steps": [
    {
      "text": "Create type request: Create and enter type editor.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type-creation"
        }
      },
      "capability": "create-motion-type"
    },
    {
      "text": "Preset-based type creation explicitly redirects into its editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "creates",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Screening",
            "Amendment settings",
            "Flags",
            "Deleted"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type-creation"
        }
      },
      "capability": "create-motion-type"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type"
        }
      },
      "capability": "create-motion-type"
    },
    {
      "text": "Edit type request: Web configuration.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type"
        }
      },
      "capability": "edit-motion-type"
    },
    {
      "text": "Type metadata/settings persist; Web section definitions remain independently editable, without API parity.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "changes",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Screening",
            "Amendment settings",
            "Flags"
          ]
        },
        {
          "entity": "section-definition",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type"
        }
      },
      "capability": "edit-motion-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/IndexController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Create and configure Motion type — User — Type

## Trigger

Configure the type the creation redirect carries into its editor.

## Outcome

The new type has saved metadata and settings.
