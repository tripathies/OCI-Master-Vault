# OCI Cost, Budgets & Lab Cleanup

## Before a lab
- Use a dedicated test compartment and appropriate sandbox tenancy.
- Review Oracle Cloud pricing, region availability, service limits and free-tier eligibility.
- Establish budgets, usage monitoring, resource tags and written teardown steps.
- Confirm whether resources are shared before changing or deleting them.
- Never place credentials or production data in lab code.

## Common cost drivers
Compute shape and uptime; boot/block volumes; backups and replication; load balancers; network egress; OKE node pools; Object Storage capacity and requests; database OCPUs, storage and backup; logs and analytics retention; streaming and AI usage.

## Cleanup checklist
- [ ] Review test compute and instance pools before termination.
- [ ] Review boot/block volumes, volume backups, public IPs and network artifacts.
- [ ] Remove lab load balancers, OKE clusters and attached resources when no longer required.
- [ ] Check retention before deleting objects and backups.
- [ ] Delete test databases only after verifying ownership and recovery needs.
- [ ] Remove lab functions, API gateways, event rules, streams, queues and connectors.
- [ ] Review monitoring/logging retention, budgets and scheduled automation.
- [ ] Reconcile usage reports and confirm remaining billable resources.

Never run broad automated deletion without reviewing compartment scope and every target resource. Budget alerts do not themselves stop usage.