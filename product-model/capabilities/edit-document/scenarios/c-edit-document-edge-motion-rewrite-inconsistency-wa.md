---
{
  "kind": "edge",
  "routes": {
    "route": "WA Motion rewrite inconsistency"
  },
  "steps": [
    {
      "text": "Edit record request: Motion rewrite inconsistency.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration"
        }
      }
    },
    {
      "text": "The Product leaves inconsistent text rewriting undone while saving the valid changed Internal note; saveMotion does not propagate the rewrite failure.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Internal note"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": [
            "Content"
          ]
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Changes"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-administration"
        }
      }
    }
  ],
  "references": [
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
      "target": "controllers/admin/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Permissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MotionEditForm.php#updateTextRewritingAmendments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MotionEditForm.php#saveMotion"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionController.php#actionUpdate"
    }
  ]
}
---

# Edit document — Motion rewrite inconsistency — WA

## Trigger

Edit document request: Motion rewrite inconsistency.

## Outcome

An unresolved dependent rewrite returns false before text-section rewriting. saveMotion does not propagate that return as a FormError: the text and dependent amendment baselines remain unchanged, while an otherwise valid Internal note and earlier account-independent details can save and the form reports saved.
