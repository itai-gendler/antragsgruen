---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "visitor",
      "effect": "changes",
      "facts": [
        "Preferred language"
      ],
      "contexts": [
        {
          "place": "web::public::consultation"
        }
      ]
    }
  ],
  "permits": [
    {
      "self": true
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    }
  ]
}
---

# Visitor language change is available to the applicable readers

A Visitor changes the language preference kept by their anonymous continuity.
