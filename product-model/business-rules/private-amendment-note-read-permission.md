---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-amendment-note",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::amendment"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php#savePrivateNote"
    }
  ]
}
---

# Private amendment note read is available to the owner

Only the owning account reads/saves its private note, with allowPrivateComments enabled for saving. The Motion scope is section/paragraph; Amendment scope is the whole selected Amendment. Empty Save removes an existing note and can create an empty new record.
