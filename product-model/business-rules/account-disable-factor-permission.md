---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "disable-second-factor",
      "contexts": [
        {
          "place": "web::authenticated::my-account"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionMyaccount"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/SecondFactorAuthentication.php#attemptRemovingSecondFactor"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "views/user/my_account.php"
    }
  ]
}
---

# Personal factor removal validates a currently enrolled key

Removal checks the supplied code against currently enrolled keys and removes the matching key only; an absent enrollment or unmatched code reports an error. Forced enrollment hides the removal control in My account. The save handler and attemptRemovingSecondFactor do not add a forced-enrollment refusal to this submitted removal operation; UI availability is not asserted as a backend authorization guarantee. Owner authority and supportsSecondFactorAuth are governed by the personal factor-control permission Rule.
