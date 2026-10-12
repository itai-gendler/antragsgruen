---
{
  "kind": "edge",
  "routes": {
    "route": "WA Forced-enrollment control differs from handler"
  },
  "steps": [
    {
      "text": "The User submits the personal removal request with a matching factor code although forced enrollment hides its control.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "The forced-enrollment configuration hides the removal control but the submitted operation has no additional forced-enrollment check.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "installation-settings",
          "effect": "reads",
          "facts": [
            "Authentication configuration"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Second-factor configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    },
    {
      "text": "The matching enrolled key is removed by the handler; the UI’s hidden-control condition does not refuse this submitted operation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Second-factor configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::my-account"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/LoginUsernamePasswordForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/SecondFactorAuthentication.php#attemptRemovingSecondFactor"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionMyaccount"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "views/user/my_account.php"
    }
  ]
}
---

# Disable second factor — Forced-enrollment control differs from handler — WA

## Trigger

A current account with an enrolled key submits the personal removal request with a matching code while forced enrollment hides its removal control.

## Outcome

The matching key is removed. The shipped UI hides the control under forced enrollment, but the submitted save operation has no corresponding forced-enrollment refusal. No continuing ability to avoid required enrollment on later sign-in is promised.
