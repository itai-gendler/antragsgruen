---
{
  "entities": [
    {
      "entity": "page",
      "shows": [
        "Address",
        "Title",
        "Contents",
        "Scope",
        "Menu inclusion",
        "Read policy",
        "Editing information",
        "Files"
      ],
      "collects": [
        "Title",
        "Contents",
        "Scope",
        "Menu inclusion",
        "Read policy"
      ]
    },
    {
      "entity": "document-group",
      "shows": [
        "Name",
        "Order",
        "Container"
      ]
    },
    {
      "entity": "document",
      "shows": [
        "Title",
        "Filename",
        "Content",
        "Address",
        "Container"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationFileGroup.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationFile.php"
    }
  ]
}
---

# Page

Selected content and files disclosed by the applicable scope and reading policy.
