---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "check-proposed-change-conflicts",
      "contexts": [
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
      "target": "models/db/IProposal.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/ProposedProcedureController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/ProposedChangeForm.php"
    }
  ]
}
---

# Conflict checking is advisory and stops above 100 candidates.

The checker reports detected collisions for its selected current/proposed alternatives. More than 100 candidates returns the implemented maximum-100 error. Its result does not certify semantic agreement or cover every paragraph-sharing case.
