---
buttons:
  - title: Hands on Lab - Download
    icon: material-file-download-outline
    attributes:
      class: md-content__button md-icon
      href: ../hands-on-labs.pdf
      target: _blank
---

# FortiCNAPP OPAL Lab

Welcome to the FortiCNAPP OPAL Lab. This guide walks you through building, testing, and optionally uploading a custom OPAL policy using the FortiCNAPP CLI.

---

## 🔍 Opal Overview

OPAL is FortiCNAPP’s infrastructure-as-code (IaC) static analyzer based on the **OPA** framework and **Rego** language. It evaluates AWS, Azure, GCP, and Kubernetes configurations for potential security and compliance violations **before deployment**.

You can create custom OPAL policies in Rego and scan your IaC with them using the FortiCNAPP CLI.

!!! info "Supported Frameworks"
    | Framework              | Format         |
    |------------------------|----------------|
    | Azure Resource Manager | JSON           |
    | CloudFormation         | JSON, YAML     |
    | Kubernetes             | YAML           |
    | Terraform              | HCL, JSON Plan |

OPAL supports CI/CD tools such as **Jenkins**, **CircleCI**, and **AWS CodePipeline** via the Lacework FortiCNAPP CLI.

### 🧠 How It Works

- Converts your IaC into a normalized data structure
- Evaluates that structure against custom Rego policies
- Outputs results in **CLI**, **JSON**, or **JUnit.xml**
- Can be used standalone or integrated into pipelines
- Policy config can be toggled in `config.yaml` or the UI

---

## 🧪 What You'll Learn

- How to install and configure the FortiCNAPP CLI
- How to generate a custom OPAL policy with tests
- How to run and debug policy test results
- How to upload policies and use them in scans

---

## 🚀 Fast-Forward: Pressed on Time? Try This

Not interested in following the full guide and just want a working demo?

!!! tip "Skip the setup"
    A working OPAL policy, metadata, and test cases are included in a GitHub repo:

    🔗 [OPAL Demo](https://github.com/40docs/lab_forticnapp_opal)

Clone it and run:

```bash
git clone https://github.com/40docs/lab_forticnapp_opal.git
cd lab_forticnapp_opal/policies
lacework iac policy test -d opal/sample_custom_policy
```
