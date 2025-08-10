# FortiCNAPP OPAL Demo

[![Documentation](https://img.shields.io/badge/docs-available-green.svg)](https://docs.40docs.com/docs-forticnapp-opal-demo/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Educational content and hands-on laboratory materials for **FortiCNAPP OPAL** (Open Policy Agent Language) demonstrations.

## 🎯 Overview

This repository provides comprehensive training materials for learning FortiCNAPP's Infrastructure-as-Code (IaC) security scanning capabilities using the OPAL framework. OPAL leverages the Open Policy Agent (OPA) and Rego language to evaluate cloud configurations for security and compliance violations **before deployment**.

### What You'll Learn

- **OPAL Framework**: Understanding FortiCNAPP's IaC static analyzer
- **Custom Policy Development**: Creating security policies using Rego language
- **Multi-Cloud Security**: Scanning AWS, Azure, GCP, and Kubernetes configurations
- **CI/CD Integration**: Embedding security scanning in development pipelines

## 🚀 Quick Start

### Fast-Forward Demo

Want to jump straight into action? A complete working example is available:

```bash
# Clone the companion lab repository
git clone https://github.com/40docs/lab-forticnapp-opal.git
cd lab-forticnapp-opal/policies

# Run the demo (requires FortiCNAPP CLI)
lacework iac policy test -d opal/sample_custom_policy
```

### Full Learning Path

For the complete educational experience, follow the structured hands-on labs:

1. **[Prerequisites](hands-on-labs/00-prerequisites.md)** - Setup FortiCNAPP CLI and authentication
2. **[Environment Setup](hands-on-labs/01-setup.md)** - Configure your development environment  
3. **[Interactive Demo](hands-on-labs/02-demo.md)** - Build, test, and deploy custom OPAL policies

## 📋 Prerequisites

### Required Accounts & Tools

| Requirement | Description | Installation Guide |
|-------------|-------------|--------------------|
| **FortiCNAPP Account** | Valid account with API key/secret | [Prerequisites Guide](hands-on-labs/00-prerequisites.md#accounts-and-access) |
| **FortiCNAPP CLI** | Command-line interface with IaC component | [CLI Installation](hands-on-labs/00-prerequisites.md#required-tools) |
| **Terraform** | For testing IaC configurations | [terraform.io](https://terraform.io/downloads) |

### Supported Frameworks

OPAL analyzes multiple Infrastructure-as-Code formats:

| Framework | Supported Formats | Use Cases |
|-----------|------------------|-----------|
| **Terraform** | HCL, JSON Plan | Multi-cloud infrastructure |
| **AWS CloudFormation** | JSON, YAML | AWS-specific deployments |
| **Azure Resource Manager** | JSON | Azure resource management |
| **Kubernetes** | YAML | Container orchestration |

## 🧪 Repository Structure

```
docs-forticnapp-opal-demo/
├── index.md                    # Landing page with CSS styling
├── hands-on-labs/
│   ├── index.md               # Lab overview and fast-forward option
│   ├── 00-prerequisites.md    # Setup requirements and CLI installation
│   ├── 01-setup.md           # Environment configuration
│   └── 02-demo.md            # Interactive demonstration workflow
├── *.css                     # Custom styling for Material Design
└── *.gif                     # Visual demonstrations and outputs
```

## 💡 Key Features

### OPAL Framework Capabilities

- **Multi-Framework Support**: Scan Terraform, CloudFormation, ARM templates, and Kubernetes manifests
- **Custom Policy Engine**: Write security rules in Rego language
- **CI/CD Integration**: Support for Jenkins, CircleCI, AWS CodePipeline
- **Flexible Output**: CLI, JSON, or JUnit XML formats
- **Policy Management**: Upload, version, and organize policies through UI or CLI

### Educational Approach

- **Progressive Learning**: Structured path from basics to advanced usage
- **Hands-On Practice**: Real-world examples and interactive exercises
- **Multiple Learning Styles**: Detailed walkthroughs and quick demos
- **Visual Support**: GIFs and screenshots for complex procedures

## 🔧 Development Workflow

### Policy Development Cycle

```bash
# 1. Generate new policy template
lacework iac policy generate

# 2. Develop custom Rego rules
# Edit policy files with your security requirements

# 3. Create test cases
# Define test scenarios for policy validation

# 4. Test locally
lacework iac policy test -d /path/to/policy

# 5. Upload to FortiCNAPP (optional)
lacework iac policy upload -f policy.tar.gz

# 6. Scan infrastructure
lacework iac scan -p config.yaml
```

### Testing Strategy

- **Unit Testing**: Validate individual policy rules with test cases
- **Integration Testing**: Test policies against real IaC configurations
- **CI/CD Integration**: Automated scanning in deployment pipelines
- **Regression Testing**: Ensure policy updates don't break existing scans

## 🌐 Integration with 40docs Platform

This repository is part of the **40docs Documentation as Code ecosystem**:

- **GitOps Deployment**: Content automatically deployed via Flux v2
- **Material Design**: Consistent theming across documentation platform
- **Claude Orchestrator**: AI-assisted content management and updates
- **Multi-Repository**: Integrated with 25+ specialized documentation repos

## 📚 Additional Resources

### FortiCNAPP Documentation
- [Official FortiCNAPP CLI Documentation](https://docs.lacework.com/cli)
- [OPAL Policy Development Guide](https://docs.lacework.com/iac-security)
- [Rego Language Reference](https://www.openpolicyagent.org/docs/latest/policy-language/)

### Community Resources
- [OPA Community](https://www.openpolicyagent.org/community/)
- [Rego Playground](https://play.openpolicyagent.org/)
- [Policy Examples Repository](https://github.com/open-policy-agent/library)

## 🤝 Contributing

This educational content is maintained as part of the 40docs platform. For contributions:

1. **Content Updates**: Submit pull requests with improved explanations or examples
2. **Lab Enhancements**: Add new scenarios or troubleshooting guides
3. **Visual Materials**: Contribute screenshots, diagrams, or demonstration videos

## 📄 License

This documentation is available under the MIT License. See the [LICENSE](LICENSE) file for details.

---

**Part of the [40docs](https://github.com/40docs) Documentation as Code Platform** | **Powered by GitOps & Kubernetes**