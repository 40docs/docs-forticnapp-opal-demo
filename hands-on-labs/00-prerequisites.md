# Prerequisites

Before you begin building and testing custom OPAL policies in FortiCNAPP, ensure the following prerequisites are met.

## 🧾 Accounts and Access

!!! note "FortiCNAPP Access"
    - A valid **FortiCNAPP (formerly Lacework)** account  
    - API **Key** and **Secret** with IaC Policy permissions

## 🛠 Required Tools

| Tool            | Description                             |
|-----------------|-----------------------------------------|
| `lacework` CLI  | FortiCNAPP CLI with IaC component       |
| `terraform`     | CLI to execute test configurations      |
| Text editor     | Recommended: VS Code or Vim             |

!!! tip "Install CLI"
    Follow [FortiCNAPP CLI installation guide](https://docs.lacework.com/cli/install) to install the CLI.

## 💻 Environment

- Unix-based terminal (macOS, Linux, or WSL on Windows)
- Internet connection (for policy downloads)

## 🔧 Optional Tools

!!! info "Recommended Tools"
    - `tree`: To view directory structures
    - `jq`: To parse CLI JSON output

