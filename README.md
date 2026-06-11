# AWX Execution Environment

A custom [Ansible Execution Environment](https://docs.ansible.com/automation-controller/latest/html/userguide/execution_environments.html) built on UBI 9 / Python 3.12.

## Contents

| File | Purpose |
|------|---------|
| `execution-environment.yml` | EE definition (base image, dependency sources, build steps) |
| `requirements.yml` | Ansible collections (`ansible.posix`, `community.general`, `community.crypto`) |
| `requirements.txt` | Additional Python packages |
| `bindep.txt` | System packages (`git`, `openssh-clients`) |

## Build

```bash
ansible-builder build -t awx-ee-mee:latest
```

Requires [ansible-builder](https://ansible-builder.readthedocs.io/) (`pip install ansible-builder`).

## Base image

`registry.access.redhat.com/ubi9/python-312:latest` with `ansible-core >= 2.17` and `ansible-runner`.
