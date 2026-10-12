---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-motion-note",
      "effect": "changes",
      "facts": [
        "Text"
      ],
      "contexts": [
        {
          "place": "web::authenticated::motion"
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
      "target": "controllers/MotionActionsTrait.php#savePrivateNote"
    }
  ]
}
---

# Private motion note change is available to the owner

Only the owning account reads/saves its private note, with allowPrivateComments enabled for saving. The Motion scope is section/paragraph; Amendment scope is the whole selected Amendment. Empty Save removes an existing note and can create an empty new record.
