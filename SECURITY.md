Security Policy — PidonOS (turtleboyagain120/PidonOS)
=====================================================

Purpose
-------
PidonOS is distributed under the Apache-2.0 license (https://github.com/turtleboyagain120/PidonOS).
This Security Policy tells you how to report security vulnerabilities, what information to include, how we triage and respond, and how we publish fixes and advisories. We welcome responsible disclosure and appreciate reports that help keep users and downstream projects safe.

How to report a vulnerability (preferred ways)
-----------------------------------------------
1) GitHub Security Advisory (preferred, private):
   - Use the "Security" → "Advisories" feature in this repository to create a private security advisory.
     (This keeps details private until a coordinated disclosure.)
   - If you cannot access the Security Advisories flow, email the maintainers privately (see "Maintainers" below) or open a support ticket via the project homepage if available.

2) If you must contact outside GitHub:
   - Provide the same data described below; do NOT publicly disclose the vulnerability (do not open a public Issue or PR describing the vulnerability) until a fix is released or coordinated disclosure completes.

What to include in a report (required/repro steps & commands)
-------------------------------------------------------------
Provide as much of the following as possible — this speeds triage and reduces back-and-forth:

- Identification
  - Repository: turtleboyagain120/PidonOS
  - Affected version/commit: output of:
    - git rev-parse --short HEAD
    - git log -1 --pretty=format:'%h %ad %s' --date=short
- Environment & runtime
  - OS and kernel: uname -a
  - Runtime and version (Node/Python/Go/etc.): e.g. node --version, python3 --version, go version
  - If running in container: docker --version; docker images; docker run command used
- Exact steps to reproduce (minimal, step-by-step). Prefer a short script or Dockerfile that reproduces the issue.
- Proof-of-concept (PoC): minimal code or commands that reliably trigger the issue (attach files or a private Gist).
- Logs and error output (redact sensitive data if needed).
  - Example commands:
    - journalctl -u pidonos.service --no-pager --since "1 hour ago"
    - docker logs <container-id> --tail 200
    - kubectl -n pidonos logs <pod-name> --tail=200
- Dependency list and SBOM (if relevant):
  - Node: npm ls --all --json > node-deps.json
  - Python: pip freeze > pip-freeze.txt
  - Go: go list -m all > go-mod-list.txt
  - Or generate SBOM: syft dir:. -o spdx-json > sbom-spdx.json
- Network captures (if applicable): tcpdump -w capture.pcap 'port 80 or port 443' (only if safe/legal to do)
- CVSS estimate (optional): give an initial severity opinion (Low/Medium/High/Critical) and reasoning.

Triage & response process (what maintainers will do)
----------------------------------------------------
- Acknowledgement: We will ack receipt of any valid report within 48 hours. If you don’t hear from us in 48 hours, follow up via the same private channel.
- Triage: We classify severity (Low/Medium/High/Critical) and reproduce the issue. We assign an internal ticket and estimate remediation time.
- Fix: We aim to publish an initial patch or mitigation within:
  - Critical: 7 calendar days (or sooner if a hotfix is needed)
  - High: 30 calendar days
  - Medium/Low: depending on impact, scheduled into regular releases
- Disclosure: We coordinate public disclosure after a fix is available and downstream consumers have reasonable time to upgrade. Default disclosure window is 90 days unless immediate public interest or exploit makes shorter timelines necessary.
- CVE: For issues that merit a CVE (severity High/Critical or widespread impact), maintainers will request a CVE and include it in the advisory.

Responsible disclosure rules (askers & reporters)
------------------------------------------------
- Do not publicly disclose vulnerability details (issue text, PRs, social media) before a coordinated disclosure.
- If you accidentally disclose publicly, notify maintainers immediately so we can accelerate mitigation and disclosure.
- We will not take legal action for good faith security research. Please follow these steps and avoid destructive testing on production infrastructure that you do not own.

Maintainer contacts & privacy
-----------------------------
- Primary contact channel: GitHub Security Advisories for this repository (recommended).
- If you cannot use Advisories, open a private communication channel via the project homepage (https://guns.lol/turtleboyagain) or attach PoC to an encrypted message. Do not include credentials or unrelated private data in your initial report.
- Maintainers will keep reporter identity confidential on request and offer credit in advisory release notes unless the reporter requests anonymity.

When to open a public Issue vs when to open a PR (security guidance)
-------------------------------------------------------------------
- Do NOT open a public Issue describing a vulnerability or PoC. Public Issues disclose attack details to potential attackers and hamper coordinated fixes.
- Do open a public Issue when:
  - The report is NOT security-sensitive (typo, non-exploitable documentation bug, feature request).
  - You need help using the software or deploying it safely.
- Do NOT submit a PR that publicly includes a fix with vulnerability details before coordinated disclosure. A PR may reveal the vulnerability in code or commit messages.
- Submit a PR if:
  - You have a non-sensitive improvement/fix (no security exploit details), e.g., test cleanup, docs, formatting, dependency upgrades that are routine.
  - You have a safe, non-sensitive bugfix that the maintainers asked you to submit as part of coordinated remediation (maintainers may create a private fork or branch for testing).
- Best practice for fixes: coordinate privately with maintainers first (via Security Advisories); maintainers will either accept a PR into a special private branch or ask you to provide a patch privately, then publish a public PR when disclosure is planned.

Commands & quick toolkit (useful to include with reports)
--------------------------------------------------------
- Basic repo and build info:
  - git rev-parse --short HEAD
  - git status --porcelain
  - git log -n 5 --pretty=format:'%h %ad %s' --date=short
- Environment & process:
  - uname -a
  - lsb_release -a || cat /etc/os-release
  - node --version | python3 --version | go version
- Reproduction & logs:
  - docker run --rm -p 3000:3000 ghcr.io/turtleboyagain120/pidonos:latest
  - curl -v http://127.0.0.1:3000/healthz
  - kubectl -n pidonos get pods -o wide
  - kubectl -n pidonos logs <pod-name> --tail=200
- Dependency & SBOM:
  - npm ci --ignore-scripts && npm ls --all --json > node-deps.json
  - syft dir:. -o spdx-json > sbom-spdx.json
  - trivy fs --format json -o trivy-repo.json .
- Evidence packaging:
  - tar czf pidon-report-<short-sha>.tar.gz sbom-spdx.json node-deps.json trivy-repo.json capture.pcap logs/*.txt

Disclosure & credit
-------------------
- We value coordinated disclosure. If you report a vulnerability responsibly, we will:
  - Work to fix and release a patch.
  - Credit you in the advisory/release notes unless you request anonymity.
  - Provide follow-up communication about CVE assignment or mitigation details.

When to use the GitHub "Security" tab vs "Discussions"/Wiki ("teach") for security
----------------------------------------------------------------------------------
- Use the GitHub "Security" tab (Security Advisories) when:
  - Reporting a vulnerability privately.
  - Publishing a coordinated security advisory after a fix is ready.
  - Viewing Dependabot alerts or secret scanning results for the repository.
- Use "Discussions" or the Wiki (the repo "teach" resources) when:
  - Publishing non-sensitive learning materials: secure deployment guides, hardening steps, “how to run PidonOS safely,” recommended platform-specific configurations.
  - Creating step-by-step tutorials, secure-by-default configuration examples, threat model write-ups, and training content for contributors/users.
- Why separate them:
  - Security tab = private/official incident handling and advisories.
  - Discussions/Wiki = public teaching, general best practices, and community Q&A that help users avoid security issues without exposing vulnerabilities.

Policy versioning & review
--------------------------
- Last updated: <insert date here>
- Maintainers will review security policy annually or after any significant incident.
- For questions about this policy, open a non-sensitive Issue titled "Security policy question" or contact maintainers via the Security Advisories flow.

Thank you
---------
Thank you for helping keep PidonOS secure. Responsible researchers and contributors improve the project for everyone.
