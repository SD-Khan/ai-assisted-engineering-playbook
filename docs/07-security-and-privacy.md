# Security & Privacy

AI-assisted development introduces unique risks: prompts often become accidental data leaks.

This framework enforces safe prompting and review discipline.

---

## Non-negotiables

- Never paste secrets, tokens, credentials into prompts
- Never paste customer/client identifiers or sensitive business data
- Use sanitized examples and placeholders
- Avoid copying logs that contain PII (redact first)
- Treat AI output as untrusted until reviewed

---

## Safe prompting patterns

- Replace real identifiers with placeholders:
  - TENANT_ID, USER_ID, ORDER_ID
- Replace real URLs with example domains
- Redact emails/phone numbers
- Prefer minimal reproduction snippets over full dumps

---

## Security review checklist (quick)

- auth and authorization enforced where needed?
- least privilege maintained?
- input validation explicit?
- sensitive data not logged?
- external calls safe and bounded?
- no new risky dependencies?