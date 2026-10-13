---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "close-voting",
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
      "target": "models/majorityType/SimpleMajority.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    }
  ]
}
---

# A voting item passes by simple majority.

Under simple majority, a closed item is accepted when its Yes votes exceed its No votes; otherwise it is rejected. Abstentions do not count.

The result is computed when the ballot closes, only for items answered Yes/No or Yes/No/Abstention. An item whose quorum is missed records the missed quorum instead.
