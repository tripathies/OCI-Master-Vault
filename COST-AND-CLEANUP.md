# OCI Cost, Budgets & Lab Cleanup

## Before a lab
- Use a dedicated test compartment and appropriate sandbox tenancy.
- Review Oracle Cloud pricing, region availability, service limits and free-tier eligibility.
- Establish budget thresholds, usage monitoring, resource tags and a written teardown checklist.
- Confirm whether any resources are shared before modifying or deleting them.
- Do not store credentials or production data in lab code.

## Common cost drivers
Compute instance shape and uptime; boot and block volumes; backups and replication; load balancers; network egress and connectivity; OKE node pools; Object Storage capacity and requests; database OCPUs/storage/backup; logs and analytics ingestion/retention; streaming and AI usage.

## Cleanup checklist
- [ ] Terminate lab compute only after confirming it is not shared or required.
- [ ] Review boot/block volumes, volume backups and public IP/network artifacts.
- [ ] Remove lab load balancers, instance pools, OKE clusters and attached resources where applicable.
- [ ] Verify storage lifecycle/retention before deleting objects.
- [ ] Delete test databases only after confirming backup and ownership requirements.
- [ ] Review functions, API gateways, event rules, streams, queues and connectors.
- [ ] Check logging/monitoring retention, budgets and scheduled automation.
- [ ] Reconcile actual usage and confirm remaining billable resources.

Never run broad automated deletion without reviewing compartment scope and every target resource. Budget notifications do not themselves stop usage.
