# Working instructions

- Read README.md and docs/PLAN.md before changing scope.
- Confirm whether a command executes on Windows or in the RHEL guest. The project targets RHEL; Windows checks do not establish RHEL recovery behavior.
- Explain a bounded task, let the learner attempt it, review the output and add one useful variation. Label AI-assisted work accurately.
- Keep planned capabilities distinct from implemented and verified behavior. Update evidence only after an actual run.
- Use disposable synthetic data. Keep backup repositories, credentials, private logs and generated filesystem images outside tracked files.
- Preserve SELinux and firewall protections. Introduce privileged storage operations only in a separately identified disposable lab.
- Keep the first milestone focused on the file-recovery contract. Introduce systemd, application recovery and storage profiles when their prerequisites are verified.
- Use concise documentation that helps another operator reproduce, explain or recover the task.
