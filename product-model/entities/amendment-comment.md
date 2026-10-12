---
{
  "domain": "motions-and-amendments",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentComment.php"
    }
  ]
}
---

# Amendment comment

Amendment comment information kept by Antragsgrün.

## Information kept

- **Author** — Account or anonymous author.
- **Contact** — Author contact.
- **Text** — Document-level comment contents.
- **Reply** — Parent comment on this document.
- **Screening** — Pending, visible or deleted condition.
- **Notification information** — Comment subscription information.

## States

### Pending

Awaiting comment screening.

### Visible

Published comment.

### Deleted

Marked deleted.
