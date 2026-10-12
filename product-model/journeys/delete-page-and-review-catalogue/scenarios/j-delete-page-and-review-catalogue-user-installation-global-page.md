---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Installation-global page"
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
      },
      "capability": "delete-page"
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
      },
      "capability": "delete-page"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::page-administration"
        }
      },
      "capability": "delete-page"
    },
    {
      "text": "Browse pages request: Administrative page catalogue.",
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
      "capability": "browse-pages"
    },
    {
      "text": "The administrative catalogue presents addressed pages and scopes.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
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
      "capability": "browse-pages"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/ConsultationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    }
  ]
}
---

# Delete Page and review catalogue — User — Installation-global page

## Trigger

Delete the addressed page and review its catalogue.

## Outcome

The selected page is removed and the catalogue is presented.
