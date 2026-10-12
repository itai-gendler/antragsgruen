---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative page catalogue"
  },
  "steps": [
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
      }
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
      }
    }
  ],
  "references": [
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Browse pages — Administrative page catalogue — WA

## Trigger

Browse pages request: Administrative page catalogue.

## Outcome

The administrative catalogue presents addressed pages and scopes.
