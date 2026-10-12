---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Page"
  },
  "steps": [
    {
      "text": "Create page request: Blank addressed page and editor hand-off.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page-administration"
        }
      },
      "capability": "create-page"
    },
    {
      "text": "A unique valid address creates a blank scoped page and redirects into its editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "creates",
          "facts": [
            "Address",
            "Title",
            "Contents",
            "Scope",
            "Menu inclusion",
            "Read policy",
            "Editing information",
            "Files"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page-administration"
        }
      },
      "capability": "create-page"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::page"
        }
      },
      "capability": "create-page"
    },
    {
      "text": "Edit page request: Scoped page.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page"
        }
      },
      "capability": "edit-page"
    },
    {
      "text": "Selected scoped/global contents and configuration persist.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "changes",
          "facts": [
            "Title",
            "Contents",
            "Scope",
            "Menu inclusion",
            "Read policy",
            "Editing information"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::page"
        }
      },
      "capability": "edit-page"
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

# Create and edit Page — User — Page

## Trigger

Fill the blank addressed page creation opens for editing.

## Outcome

The new addressed page has saved contents.
