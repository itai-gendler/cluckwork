---
availability:
- place: operator-cli
references:
- kind: code
  role: implementation
  target: src/Cluckwork.Api/Cli/ProvisionAccountCliCommand.cs
- kind: code
  role: implementation
  target: src/Cluckwork.Infrastructure/Modules/Access/Identity/AccountProvisioner.cs
---

# Provision a farm

Create a new farm with its farm code, its ten standard egg grades, its six packed units and its first Owner, in one transaction. The Owner gets a printed one-time password; the farm starts in UTC.
