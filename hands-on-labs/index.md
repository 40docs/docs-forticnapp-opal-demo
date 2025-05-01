---
buttons:
  - title: Hands on Lab - Download
    icon: material-file-download-outline
    attributes:
      class: md-content__button md-icon
      href: ../hands-on-labs.pdf
      target: _blank
---

# FortiCNAPP OPAL CLI Demo

Welcome to the FortiCNAPP OPAL CLI demo. This guide provides step-by-step instructions to get started with OPAL using the FortiCNAPP CLI.

## Sections

- [Prerequisites](00-prerequisites.md)
- [Setup](01-setup.md)
- [Demo](02-demo.md)

### 🚀 Fast-Forward: Pressed on time? Try this

Not interested in following along with the full guide and just want a working demo of FortiCNAPP OPAL?

!!! tip "Practical Demo Available"
    We've condensed the examples in this lab into a ready-to-run GitHub repository:

    🔗 [lab_forticnapp_opal GitHub Repo](https://github.com/40docs/lab_forticnapp_opal)

    This includes:
    - Pre-built `metadata.yaml` and `policy.rego`
    - Ready-to-use `pass/` and `fail/` Terraform test cases
    - Directory structure compatible with the CLI

To test it:

```bash
git clone https://github.com/40docs/lab_forticnapp_opal.git
cd lab_forticnapp_opal/policies
lacework iac policy test -d opal/sample_custom_policy
```

!!! note
    This skips the setup wizard and lets you see policy test results immediately.
