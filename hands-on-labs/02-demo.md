# Demo

## Testing and running custom policies

Now that you've created your custom OPAL policy, test it with Terraform examples.

## 1. Create Test Inputs

### ✅ Passing Test

```bash
mkdir -p ../policies/opal/sample_custom_policy/terraform/tests/pass
```

Create `main.tf`:

```hcl
resource "aws_s3_bucket" "test" {
  bucket = "test-bucket"
  logging {
    target_bucket = "example"
  }
}
```

### ❌ Failing Test

```bash
mkdir -p ../policies/opal/sample_custom_policy/terraform/tests/fail
```

Create `main.tf`:

```hcl
resource "aws_s3_bucket" "test" {
  bucket = "test-bucket"
  logging {
    target_bucket = "bad-example"
  }
}
```

!!! note
    You can include either passing, failing, or both test types.

## 2. Run Policy Tests

```bash
lacework iac policy test -d ../policies/opal/sample_custom_policy
```

Expected output includes test results for each `pass/` and `fail/` case.

## 3. Debug with Rego Print

Add a print statement to your policy:

```rego
print(sprintf("target_bucket: %s", [input.logging[_].target_bucket]))
```

Output example:

```json
"print_statements": [
  {
    "Message": "target_bucket: example",
    "Line": 5,
    "PolicyFile": "/path/to/policy.rego"
  }
]
```

!!! warning "Avoid Committing Prints"
    Do not commit print statements to version control.

## 4. Upload Custom Policy

You can package and upload your entire policies directory:

```bash
lacework iac policy upload -d ../policies
```

This will replace all existing custom policies.

## 5. Use Policies with a Target Directory

Run an OPAL scan on any Terraform project:

```bash
lacework iac tf-scan opal --disable-custom-policies=false -d path/to/project
```

!!! tip
    If `-d` is not provided, the current directory is used.
