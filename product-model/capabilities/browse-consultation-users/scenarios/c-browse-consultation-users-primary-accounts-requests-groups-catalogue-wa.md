---
{
  "kind": "primary",
  "routes": {
    "route": "WA Accounts/requests/groups catalogue"
  },
  "steps": [
    {
      "text": "Browse selected item users request: Accounts/requests/groups catalogue.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "user-group",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
        }
      }
    },
    {
      "text": "The consultation account, group and pending-request catalogue is presented.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Name",
            "Email",
            "Organization",
            "Authentication identity",
            "Email confirmation",
            "Password configuration",
            "Second-factor configuration",
            "Account restrictions",
            "Vote weights",
            "Pending email change",
            "Preferred language"
          ]
        },
        {
          "entity": "user-group",
          "effect": "reads",
          "facts": [
            "Name",
            "Scope",
            "Template",
            "Selectability",
            "Permissions"
          ]
        },
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": [
            "Account",
            "Consultation",
            "Request information"
          ]
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
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

# Browse consultation users — Accounts/requests/groups catalogue — WA

## Trigger

Browse consultation users request: Accounts/requests/groups catalogue.

## Outcome

The consultation account, group and pending-request catalogue is presented.
