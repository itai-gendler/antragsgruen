---
{
  "domain": "motions-and-amendments",
  "relations": [
    {
      "entity": "amendment-text-section",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "amendment-proposed-procedure",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "amendment-comment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "private-amendment-note",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "amendment",
      "verb": "parents",
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
      "target": "models/db/Amendment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IMotion.php"
    }
  ]
}
---

# Amendment

Amendment information kept by Antragsgrün.

## Information kept

- **Base** — Base Motion and optional parent Amendment.
- **Title** — Document title and numbering/version.
- **Changes** — Changed content and baseline.
- **Reason** — Reason for changes.
- **Alternative information** — Global alternative and editorial information.
- **Initiators** — Initiating people or organizations.
- **Disposition** — Draft, administrative draft, collecting, unscreened, checked, screened, visible/invisible withdrawal, Deleted, and the stored administrative decisions Accepted, Rejected, Modified accepted, Processed, quorum results, referrals, moved/superseded/custom and assembly outcomes. Proposed procedure and voting outcome are separate facts.
- **Submission information** — Creation, submission and publication information.
- **Flags** — Fixed text and related document configuration.
- **Responsibility** — Responsible account and separate responsibility note.
- **Voting information** — Assignment, grouping, voting status and recorded voting information.
- **Internal note** — Administrative note.
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

### Deleted

Marked deleted through the document operation.
