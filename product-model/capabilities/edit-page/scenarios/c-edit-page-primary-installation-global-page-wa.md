---
{
  "kind": "primary",
  "routes": {
    "route": "WA Installation-global page"
  },
  "steps": [
    {
      "text": "Edit page request: Installation-global page.",
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
      }
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

# Edit page — Installation-global page — WA

## Trigger

Edit page request: Installation-global page.

## Outcome

Selected scoped/global contents and configuration persist.
