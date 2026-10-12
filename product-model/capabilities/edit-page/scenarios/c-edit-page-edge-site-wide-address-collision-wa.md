---
{
  "kind": "edge",
  "routes": {
    "route": "WA Site-wide address collision"
  },
  "steps": [
    {
      "text": "Edit page request: selected item-wide address collision.",
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
      "text": "Site-wide address collision is reported.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
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

# Edit page — Site-wide address collision — WA

## Trigger

Edit page request: Site-wide address collision.

## Outcome

Site-wide address collision is reported.
