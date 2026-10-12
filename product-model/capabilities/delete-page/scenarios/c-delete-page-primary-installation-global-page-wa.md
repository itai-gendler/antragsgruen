---
{
  "kind": "primary",
  "routes": {
    "route": "WA Installation-global page"
  },
  "steps": [
    {
      "text": "Delete page request: Installation-global page.",
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
      "text": "The selected scoped/global page is removed and redirects to the catalogue.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "removes"
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

# Delete page — Installation-global page — WA

## Trigger

Delete page request: Installation-global page.

## Outcome

The selected scoped/global page is removed and redirects to the catalogue.
