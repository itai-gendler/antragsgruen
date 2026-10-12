---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Email confirmation",
        "Password configuration"
      ],
      "contexts": [
        {
          "place": "web::authenticated::email-confirmation"
        },
        {
          "place": "web::public::email-confirmation"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "user"
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
      "target": "controllers/UserController.php#actionConfirmregistration"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/LoginUsernamePasswordForm.php#sendConfirmationEmail"
    }
  ]
}
---

# Account email confirmation is available in either Web context

Visitor and User can invoke confirmation of the account resolved by the supplied email/code, or resend for an actual ongoing confirmation-session target after the resend interval. Confirmation code, captcha and challenge resolution are authentication/request validation governed by the authentication invariant; no existing ownership relationship or administration grant is required to follow a valid confirmation link. Sending again keeps the account Unconfirmed and saves resend timing only after successful mail sending.
