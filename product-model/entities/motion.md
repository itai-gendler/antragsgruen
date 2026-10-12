---
{
  "domain": "motions-and-amendments",
  "relations": [
    {
      "entity": "amendment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion-text-section",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion-proposed-procedure",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion-comment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "private-motion-note",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "merge-draft",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resolution",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion",
      "verb": "precedes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supporter",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "procedure-note",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "tag",
      "verb": "carries",
      "cardinality": "many-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IMotion.php"
    }
  ]
}
---

# Motion

Motion information kept by Antragsgrün.

## Information kept

- **Title** — Document title.
- **Address** — Public address and numbering/version.
- **Text** — Document content and languages.
- **Initiators** — Initiating people or organizations.
- **Disposition** — Draft, administrative draft, collecting, unscreened, checked, screened, visible/invisible withdrawal, Deleted, and the stored administrative decisions Accepted, Rejected, Modified accepted, Processed, quorum results, referrals, moved/superseded/custom and assembly outcomes. Proposed procedure and voting outcome are separate facts.
- **Submission information** — Creation, submission and publication information.
- **Flags** — Fixed text, amendment/comment and other document configuration.
- **Protocol** — Recorded protocol and its publicity.
- **Responsibility** — Responsible account and separate responsibility note.
- **Voting information** — Assignment, grouping, voting status and recorded voting information.
- **Internal note** — Administrative note.
- **Relationships** — Type, agenda, predecessor and successor associations.
- **Public tags** — topic/amendment-classified tag associations.
- **Procedure tags** — procedure-classified tag associations.

## States

### Draft

Saved before submission confirmation.

### Collecting

Collecting official supporters.

### Unscreened

Submitted and awaiting screening.

### Screened

Screened submitted contents.

### Withdrawn

Withdrawn with the implemented disclosure.

### Modified

Source replaced through a successor workflow.

### Deleted

Marked deleted through the document operation.

### Preliminary resolution

The consolidated document has the implemented preliminary-resolution disposition; its Resolution facts are kept separately.

### Final resolution

The consolidated document has the implemented final-resolution disposition; its Resolution facts are kept separately.
