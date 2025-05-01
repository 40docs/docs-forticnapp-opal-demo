# Setup

## Creating a Custom OPAL Policy

To begin using OPAL in FortiCNAPP, install the FortiCNAPP CLI and initialize a policy project.

## 1. Install CLI and IaC Component

!!! note
    Ensure the FortiCNAPP CLI is installed. OPAL is bundled within the IaC security component.

## 2. Start the Policy Wizard

```bash
lacework iac policy create
```

Respond to prompts with:

| Prompt                  | Value                  |
|------------------------|------------------------|
| Policies directory path | `../policies`         |
| Select provider        | `aws`                  |
| Select target          | `terraform`            |
| Policy name            | `sample_custom_policy` |
| Title                  | `Sample Custom Policy` |
| Category               | `logging`              |
| ResourceType           | `aws_s3_bucket`        |
| Severity               | `medium`               |

!!! info "Naming Convention"
    Policy names must be lowercase with underscores (e.g., `sample_custom_policy`).

A directory structure like this is created:

```text
../policies/opal/sample_custom_policy/terraform/
../policies/opal/sample_custom_policy/terraform/tests/
```

## 3. Review `metadata.yaml`

Located at:

```text
../policies/opal/sample_custom_policy/metadata.yaml
```

It includes:

```yaml
category: logging
checkTool: opal
checkType: terraform
description: "example policy"
provider: aws
severity: medium
title: "Sample Custom Policy"
```

## 4. Add OPAL Policy Logic

Edit `policy.rego`:

```rego
package policies.sample_custom_policy

input_type := "tf"
resource_type := "aws_s3_bucket"
default allow = false

allow {
  input.logging[_].target_bucket == "example"
}
```

