---
{
  "domain": "speaking-lists",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueueItem.php"
    }
  ]
}
---

# Speech

Speech information kept by Antragsgrün.

## Information kept

- **Identity** — Account or anonymous cookie identity.
- **Name** — Applicant/speaker name.
- **Subqueue** — Assigned subqueue.
- **Point of order** — Whether this is a point-of-order application.
- **Application order** — Waiting order and application time.
- **Slot** — Assigned speaking slot.
- **Start time** — Speech start.
- **Stop time** — Speech stop.
