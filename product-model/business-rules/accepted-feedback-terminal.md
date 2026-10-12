---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "accept-proposed-procedure",
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
      "id": "reject-proposed-procedure",
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
      "id": "record-proposer-acceptance",
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

# Accepted initiator feedback is terminal on that response path.

An accepted response blocks later initiator-path accept/reject changes. The separate Limited-procedure staff-recording route can set/reset the response and does not inherit that terminal lock.
