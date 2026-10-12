---
{
  "kind": "primary",
  "routes": {
    "route": "WA Ordinary successor"
  },
  "steps": [
    {
      "text": "Merge amendments request: Ordinary successor.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [],
          "as": "source"
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      }
    },
    {
      "text": "The Product saves the working consolidation and creates a Draft successor preview with the consolidated sections and protocol.",
      "kind": "product",
      "actor": "user",
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      },
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "changes",
          "facts": [
            "Text",
            "Selections",
            "Handled warnings",
            "Dispositions",
            "Voting information",
            "Protocol",
            "Removed sections",
            "Saved date"
          ]
        },
        {
          "entity": "motion",
          "as": "successor",
          "effect": "creates",
          "to": "Draft",
          "facts": [
            "Title",
            "Address",
            "Text",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Protocol",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Relationships",
            "Public tags",
            "Procedure tags"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "creates",
          "with": "successor",
          "facts": [
            "Section identity",
            "Language",
            "Content",
            "Activity",
            "Publicity"
          ]
        }
      ]
    },
    {
      "text": "The User confirms the consolidated text, Amendment decisions, recorded decision totals and selected outcome.",
      "kind": "actor",
      "actor": "user",
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      },
      "entities": [
        {
          "entity": "motion",
          "as": "successor",
          "effect": "reads",
          "facts": [
            "Text",
            "Disposition"
          ]
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Disposition",
            "Voting information"
          ]
        }
      ]
    },
    {
      "kind": "product",
      "actor": "user",
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      },
      "entities": [
        {
          "entity": "motion",
          "as": "successor",
          "effect": "changes",
          "from": "Draft",
          "to": "Screened",
          "facts": [
            "Address",
            "Disposition",
            "Voting information",
            "Public tags"
          ]
        },
        {
          "entity": "motion",
          "as": "source",
          "effect": "changes",
          "facts": [
            "Address",
            "Disposition"
          ],
          "from": "Screened",
          "to": "Modified"
        },
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Disposition",
            "Voting information"
          ]
        },
        {
          "entity": "merge-draft",
          "effect": "changes",
          "facts": [
            "Deleted"
          ]
        }
      ],
      "text": "Confirmation transfers the source address to the Screened successor and marks the screened source Modified. Selected visible Amendment decisions and decision totals are saved; the working Merge draft is marked Deleted."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionMergingTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentMergingTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Draft.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Init.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Merge.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionMergingTrait.php#actionMergeAmendments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionMergingTrait.php#actionMergeAmendmentsConfirm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Merge.php#createNewMotion"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Merge.php#confirm"
    }
  ]
}
---

# Merge amendments — Ordinary successor — WA

## Trigger

Merge amendments request: Ordinary successor.

## Outcome

Confirmation transfers the source address to the Screened successor and marks the screened source Modified. Selected visible Amendment decisions and vote summaries are saved; the working Merge draft is marked Deleted.
