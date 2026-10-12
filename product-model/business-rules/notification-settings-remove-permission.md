---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "notification-settings",
      "effect": "removes"
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
      "target": "models/db/UserNotification.php"
    }
  ]
}
---

# Notification settings remove is available to the owner

The account owner reads and changes scoped subscriptions; actual document/consultation scope validation and account lifecycle cleanup remain. Notification selections are independent scoped records.
