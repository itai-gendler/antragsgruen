---
{
  "entities": [
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
