---
{
  "kind": "configuration",
  "of": "business-rule",
  "settings": [
    {
      "entity": "voting",
      "fact": "Majority and quorum"
    }
  ],
  "takesEffect": "When the ballot closes and item results are computed. The majority type can be changed only while the Voting is offline or in preparation.",
  "stability": "The type is fixed once the Voting opens. Reopening and closing again recomputes with the same type; a reset back to preparation allows a new choice.",
  "alternatives": [
    {
      "id": "simple-majority-result",
      "selectedWhen": "The Voting's majority type is Simple majority. A Voting opened without a majority type uses Simple majority."
    },
    {
      "id": "absolute-majority-result",
      "selectedWhen": "The Voting's majority type is Absolute majority."
    },
    {
      "id": "two-thirds-majority-result",
      "selectedWhen": "The Voting's majority type is Two-thirds majority."
    }
  ]
}
---

# Voting majority

Each Voting decides its items by one of three majority rules. They differ in whether abstentions count and in how large the Yes share must be, so all three stay supported.
