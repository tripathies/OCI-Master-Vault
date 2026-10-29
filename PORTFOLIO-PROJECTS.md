# OCI Portfolio Projects

Build in a sandbox, apply least privilege, track cost, and document teardown. Verify service-specific capabilities before deployment.

## 1. Secure three-tier application
Services: OCI Load Balancer, Compute, VCN/subnets, NSGs, Object Storage or database.
- [ ] Draw request and data flows.
- [ ] Separate public ingress from private workload/data tiers.
- [ ] Apply compartment-scoped IAM and least-privilege policies.
- [ ] Configure monitoring, health checks, backups and cleanup.

## 2. Hub-and-spoke connectivity
Services: VCN, DRG, LPG where appropriate, route tables, FastConnect/VPN concepts.
- [ ] Define CIDR plan and routing intent.
- [ ] Diagram allowed and denied paths.
- [ ] Document centralized inspection assumptions.
- [ ] Test route and security changes in sandbox.

## 3. OKE container platform
Services: OKE, OCIR, OCI IAM, VCN and OCI DevOps.
- [ ] Select node pool and network approach.
- [ ] Push a sample image and deploy a workload.
- [ ] Configure access, secrets and observability.
- [ ] Test rollout, scaling and recovery.

## 4. Autonomous Database application
Services: Autonomous Database, VCN private access where supported, Vault, Monitoring.
- [ ] Define connectivity and authorization model.
- [ ] Protect secrets and data access.
- [ ] Validate backup and recovery requirements.
- [ ] Document scale, performance and cost assumptions.

## 5. Governed landing zone
Services: Compartments, IAM policies, tags, quotas, Audit, Cloud Guard, Terraform/Resource Manager.
- [ ] Design compartment tree and owners.
- [ ] Create auditable least-privilege policy patterns.
- [ ] Define tagging and cost-allocation standards.
- [ ] Apply IaC and review plan changes.

## 6. Multi-region recovery design
Services: relevant database and volume backup/replication, DNS/network dependencies, Full Stack Disaster Recovery as applicable.
- [ ] Define RTO/RPO and failure scenarios.
- [ ] Document dependencies and region support.
- [ ] Write failover, validation and failback runbooks.
- [ ] Test recovery and capture evidence.

## 7. Event-driven application
Services: Events, Functions, Streaming/Queue, Notifications, Object Storage.
- [ ] Diagram event producers and consumers.
- [ ] Define retries, idempotency and error handling.
- [ ] Lock down policy scope and secrets.
- [ ] Verify telemetry and teardown.

## 8. Generative AI solution
Services: OCI Generative AI and relevant OCI IAM, logging and network controls.
- [ ] Confirm supported models, regions and access patterns.
- [ ] Define data classification and safety/evaluation requirements.
- [ ] Measure quality, latency and cost.
- [ ] Document governance and limitations.

Every project should include architecture, Terraform where appropriate, validation, security analysis, estimated/observed cost, cleanup and known limitations.