---
{
  "domain": "motions-and-amendments",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionComment.php"
    }
  ]
}
---

# Motion comment

Motion comment information kept by Antragsgrün.

## Information kept

- **Author** — Account or anonymous author.
- **Contact** — Author contact.
- **Text** — Comment contents.
- **Location** — Section and paragraph.
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
