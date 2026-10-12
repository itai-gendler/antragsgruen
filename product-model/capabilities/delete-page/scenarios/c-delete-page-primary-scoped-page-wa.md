---
{
  "kind": "primary",
  "routes": {
    "route": "WA Scoped page"
  },
  "steps": [
    {
      "text": "Delete page request: Scoped page.",
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

# Delete page — Scoped page — WA

## Trigger

Delete page request: Scoped page.

## Outcome

The selected scoped/global page is removed and redirects to the catalogue.
