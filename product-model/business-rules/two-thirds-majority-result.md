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
      "target": "models/majorityType/TwoThirdsMajority.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    }
  ]
}
---

# A voting item passes by two-thirds majority.

Under two-thirds majority, a closed item is accepted when its Yes votes are at least twice its No votes, that is at least two thirds of Yes and No together; otherwise it is rejected. Abstentions do not count.

The result is computed when the ballot closes, only for items answered Yes/No or Yes/No/Abstention. An item whose quorum is missed records the missed quorum instead.
