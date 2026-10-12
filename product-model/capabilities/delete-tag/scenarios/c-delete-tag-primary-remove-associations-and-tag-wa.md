---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove associations and tag"
  },
  "steps": [
    {
      "text": "Delete tag request: Remove associations and tag.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-settings"
        }
      }
    },
    {
      "text": "The tag and record associations are removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-settings"
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

# Delete tag — Remove associations and tag — WA

## Trigger

Delete tag request: Remove associations and tag.

## Outcome

The tag and document associations are removed.
