---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-account",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "confirm-email",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "verify-second-factor",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "recover-password",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-password",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "enable-second-factor",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-email",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "capability",
      "id": "enter-consultation-password",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
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
    }
  ]
}
---

# Authentication and confirmation follow their inspected identity-proof process.

Credentials, confirmation/recovery codes, captcha, second-factor proof, challenge expiry and consultation-password proof are verified in their actual processes. A challenge identifies its pending target, distinct from any current authenticated account. API credentials refuse required interactive prerequisites. Proof failure does not establish identity or complete the requested protected continuation.
