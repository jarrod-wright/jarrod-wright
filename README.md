# Jarrod Wright

I work on the reliability of self-hosted automation infrastructure — specifically n8n, across the three planes that have to be secured separately: the workflows, the container stack they run on, and the host underneath.

These repositories are the reference implementations I work from. They are written to be read: every non-obvious default has its reasoning next to it, and the claims are ones you can check against the shipped configuration rather than take on trust.

## The three planes

| Plane | What it covers | Repository |
|---|---|---|
| **Workflow** | Authenticated ingress, idempotency, bounded retries, dead-lettering, model-output validation, liveness | [n8n-workflow-hardening](https://github.com/jarrod-wright/n8n-workflow-hardening) |
| **Stack and container** | Compose topology, TLS termination, queue mode, secret delivery, capability drops, database privileges | [n8n-hardened-reference](https://github.com/jarrod-wright/n8n-hardened-reference) |
| **Host and OS** | CIS Ubuntu 24.04 Level 1, Server profile: SSH policy, kernel and sysctl parameters, host firewall, auditd, patch posture | [vps-hardening-reference](https://github.com/jarrod-wright/vps-hardening-reference) — in development |

They compose without overlapping, and each is incomplete on its own. A hardened stack on an unhardened host is still an unhardened host.

**Start with [n8n-hardened-reference](https://github.com/jarrod-wright/n8n-hardened-reference).** It carries the threat model and the fastest way to check whether I am telling the truth: one command that counts how many services the stack actually exposes.

## What I do

I take automation that a business already depends on and make it behave like a real system — one that fails loudly and recoverably instead of silently dropping work.

I also trade as **The Certainty Engineer**.

Engagements usually take one of three shapes:

- **A fixed-scope audit** of an existing deployment against named failure modes, with findings you can re-run yourself.
- **A hardening pass** that closes what the audit finds.
- **A migration** of live automations onto a hardened stack — parallel run, ordered credential repoint, rollback as a repoint rather than a rebuild. Never a cold cutover.

Findings come back as evidence, in the same form as the tests in these repositories. Where the value lives in the work rather than the artefact, I publish the artefact generously: the assertions are the public part, and the automation that remediates what they find is the engagement. Detection is not remediation.

## Getting in touch

**Email jarr.wright@gmail.com.** Tell me what you are running and what is breaking — the stack, roughly how much depends on it, and what went wrong most recently. I will tell you straight whether I can help and what it would take.

If you would rather ask in public first, open an issue on whichever repository you are reading. It keeps the question next to the code it is about.

*If you found me through a freelancing platform, please keep the conversation there until a contract is in place.*
