---
{
  "kind": "primary",
  "routes": {
    "route": "WA Blank addressed page and editor hand-off"
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
      }
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
      }
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

# Create page — Blank addressed page and editor hand-off — WA

## Trigger

Create page request: Blank addressed page and editor hand-off.

## Outcome

A unique valid address creates a blank scoped page and redirects into its editor.
