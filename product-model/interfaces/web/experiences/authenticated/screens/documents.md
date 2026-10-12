---
{
  "entities": [
    {
      "entity": "document-group",
      "shows": [
        "Name",
        "Order",
        "Container"
      ],
      "collects": [
        "Name",
        "Order"
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
      ],
      "collects": [
        "Title",
        "Filename",
        "Content"
      ]
    }
  ],
  "references": [
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

# Documents

File groups, ordering and uploaded-file metadata.
