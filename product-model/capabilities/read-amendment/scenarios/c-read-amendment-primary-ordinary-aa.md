---
{
  "kind": "primary",
  "routes": {
    "route": "AA Ordinary"
  },
  "steps": [
    {
      "text": "Read amendment request: Ordinary.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "The API returns Amendment title/numbering, disposition/publication information, base Motion, initiators/supporters, sections and disclosed proposed procedure.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators",
            "Disposition",
            "Submission information"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": [
            "Section identity",
            "Language",
            "Proposed content",
            "Baseline"
          ]
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Person information",
            "Organization",
            "Role",
            "Publicity"
          ]
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Title",
            "Address"
          ]
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Recommendation",
            "Visibility time",
            "Alternative text"
          ]
        },
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": [
            "Contents",
            "Baseline",
            "Proposal association"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/imotion/AmendmentDetails.php#fromEntity"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/imotion/Supporter.php#fromEntity"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/api/proposedprocedure/AmendmentProposedProcedure.php#fromAmendment"
    }
  ]
}
---

# Read amendment — Ordinary — AA

## Trigger

Read amendment request: Ordinary.

## Outcome

The API returns Amendment title/numbering, disposition/publication information, base Motion, initiators/supporters, sections and disclosed proposed procedure.
