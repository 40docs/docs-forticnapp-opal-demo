# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the **docs-forticnapp-opal-demo** repository within the 40docs platform ecosystem. It contains educational content and hands-on laboratory materials for FortiCNAPP OPAL (Open Policy Agent Language) demonstrations.

### Content Structure

This repository provides comprehensive FortiCNAPP OPAL training materials:

- **Landing Page**: `index.md` with custom CSS styling (`index.css`, `landing-page.css`)
- **Hands-on Labs Directory**: Complete learning pathway in `hands-on-labs/`:
  - `00-prerequisites.md`: FortiCNAPP CLI setup, API key configuration, and tool installation
  - `01-setup.md`: Environment setup and OPAL policy configuration procedures  
  - `02-demo.md`: Interactive demonstration and testing workflows
  - `index.md`: Lab overview with fast-forward demo option and GitHub integration
- **Visual Assets**: Instructional GIFs (`fabric-white-full.gif`, `output.gif`) for demonstration flows

### Technology Focus

**FortiCNAPP OPAL Framework**: Infrastructure-as-Code (IaC) security scanning using:
- **OPA/Rego Language**: Custom policy development for security compliance
- **Multi-Cloud Support**: AWS, Azure, GCP, and Kubernetes configuration analysis
- **CI/CD Integration**: Jenkins, CircleCI, AWS CodePipeline compatibility via FortiCNAPP CLI
- **Multiple Output Formats**: CLI, JSON, JUnit.xml for pipeline integration

## Common Development Commands

### Content Development
```bash
# This repository contains only Markdown content for MkDocs
# No build commands needed - content is deployed via GitOps to MkDocs

# Content validation (run from parent 40docs repository)
npm run lint                     # Check markdown files
npm run lint:fix                 # Auto-fix markdown issues

# Local MkDocs development (when MkDocs server is configured)
mkdocs serve                     # Start local development server  
mkdocs build                     # Build static site for testing
```

### FortiCNAPP CLI Commands (for lab content)
```bash
# CLI installation and setup (referenced in lab materials)
curl https://raw.githubusercontent.com/lacework/go-sdk/main/cli/install.sh | bash
lacework configure               # Interactive API key setup
lacework component install iac  # Enable IaC scanning component

# OPAL policy development workflow
lacework iac policy generate     # Generate new custom policy template
lacework iac policy test -d path # Test policy with test cases
lacework iac scan -p config.yaml # Scan IaC with custom policies
```

## Content Guidelines

### Markdown Structure
- **Front-matter YAML**: Use for MkDocs configuration (hide navigation, toc, footer)
- **Material Design Integration**: Leverage admonitions (`!!! info`, `!!! tip`) for enhanced presentation
- **Button Components**: Use YAML front-matter for download buttons and external links
- **Code Blocks**: Specify language for proper syntax highlighting (`bash`, `json`, `yaml`)

### Educational Content Standards
- **Progressive Learning**: Structure content from prerequisites → setup → demonstration → advanced usage
- **Multiple Learning Paths**: Provide both detailed walkthrough and fast-forward options
- **Visual Supporting Materials**: Include GIFs and screenshots for complex procedures
- **External Integration**: Link to GitHub repositories for hands-on practice

### Lab Material Requirements
- **Prerequisites Section**: Clear tool requirements and setup instructions
- **Step-by-Step Procedures**: Numbered steps with command examples and expected outputs
- **Troubleshooting Guidance**: Common issues and resolution steps
- **Fast-Forward Options**: Quick demo paths for time-constrained users

## Architecture Integration

### MkDocs Deployment
- Content deployed automatically via GitOps workflow
- CSS files served from root path (`/index.css`, `/landing-page.css`)
- Front-matter YAML controls page rendering and navigation
- Material Design components for enhanced user experience

### 40docs Ecosystem Integration
- Part of multi-repository documentation platform
- Shared CSS and theming with other documentation repositories
- Integrated with Claude orchestrator system for content management
- GitOps deployment through Flux v2 on Azure Kubernetes Service

## Key Educational Topics Covered

### OPAL Policy Development
- **Rego Language**: Custom policy creation using Open Policy Agent language
- **Policy Testing**: Test-driven development for infrastructure policies
- **Multi-Framework Support**: Terraform, CloudFormation, ARM, Kubernetes manifest scanning
- **CI/CD Integration**: Pipeline integration strategies and best practices

### FortiCNAPP CLI Usage
- **Installation Methods**: Multiple OS and package manager options
- **API Authentication**: Key generation and configuration workflows  
- **Scanning Workflows**: Local and CI/CD scanning procedures
- **Policy Management**: Upload, versioning, and organizational policy strategies

## Repository-Specific Notes

- **Read-Only Content**: This repository contains educational materials only - no executable code
- **External Dependencies**: Lab exercises reference external GitHub repository for hands-on practice
- **CSS Customization**: Custom styling for landing page presentation and Material Design integration
- **Asset Management**: GIF files provide visual demonstrations of CLI workflows and outputs