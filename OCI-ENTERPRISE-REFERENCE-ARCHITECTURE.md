# OCI Enterprise Reference Architecture

## Purpose and scope
This is an Oracle Cloud Infrastructure–specific reference for learning how to organize a governed enterprise tenancy. It is a conceptual architecture, not a deployment runbook. Adapt it to security, data residency, availability, regulatory and workload requirements.

## 1. Tenancy and governance
- Establish a resource hierarchy around compartments; define purpose, ownership, access and lifecycle of each compartment.
- Use OCI IAM policies with groups and dynamic groups; explicitly document the compartment scope and permissions each policy grants.
- Establish tagging standards, tag defaults, quotas, approved regions and budget ownership.
- Define tenancy-wide guardrails and delegated administration.

## 2. Identity and security
- Separate human identities from workload identities.
- Use identity domains and federation as appropriate to the enterprise identity model.
- Use instance principals or resource principals where supported rather than distributing long-lived credentials.
- Use OCI Vault for key and secret management, Cloud Guard for security posture/detection, Security Zones where their constraints fit, and Audit for control-plane accountability.
- Define break-glass access, review cadence and incident response.

## 3. Networking foundation
- Design VCN CIDRs and subnet segmentation to avoid overlap with on-premises and other connected networks.
- Define route tables and apply security lists and Network Security Groups (NSGs) deliberately.
- Choose Internet Gateway, NAT Gateway and Service Gateway based on traffic flows; do not expose private workloads unnecessarily.
- Use DRG for routed connectivity to on-premises, other VCNs or supported network attachments; use LPG for appropriate VCN peering scenarios.
- Choose FastConnect or Site-to-Site VPN based on connectivity, resilience, bandwidth and security requirements.
- Design DNS, private access, ingress, egress and centralized inspection explicitly.

## 4. Application and traffic
- Choose Compute instances, instance pools/autoscaling, OKE or OCI Functions according to control, runtime and operational needs.
- Put OCI Load Balancer or Network Load Balancer in front of supported workloads where the requirements fit.
- Consider OCI WAF and TLS/certificate management for public application entry points.
- Document health checks, deployment/rollback paths, capacity and failure domains.

## 5. Data and integration
- Choose Object Storage, Block Volume or File Storage Service based on access pattern and durability needs.
- Select Autonomous Database, Base Database Service, Exadata Database Service, MySQL HeatWave or Oracle NoSQL Database Cloud Service according to engine, performance, compatibility, operations and consistency needs.
- Use Events, Streaming, Queue, Notifications, Service Connector Hub and OCI Integration only where their event, messaging or integration patterns fit.
- Define encryption, key ownership, retention, backup, replication and data movement boundaries.

## 6. Delivery and operations
- Use Terraform with the OCI provider and/or OCI Resource Manager for repeatable infrastructure, with protected state, reviewed plans and controlled credentials.
- Use OCI DevOps where suitable for build/deploy pipelines and rollout controls.
- Use Monitoring, Alarms, Logging, Logging Analytics, Audit, Cloud Advisor and cost reports to provide operational evidence.
- Define service ownership, SLOs, dashboards, pager routing, runbooks and change controls.

## 7. Resilience and disaster recovery
- Determine availability domain and fault domain design from region-specific OCI capabilities.
- Define RTO/RPO per workload and choose backup, replication, warm standby or active patterns based on business requirements.
- Verify database and volume recovery mechanics per service.
- Test restoration and failover; a configured backup or replicated copy alone does not demonstrate recoverability.
- Document DNS/network changes, access prerequisites, dependencies and failback.

## 8. Architecture decisions
| Decision | Questions to answer |
|---|---|
| Compartment model | What teams, environments, services or data classes need separate governance? |
| Network topology | Which paths must be public, private, transitive, inspected or denied? |
| Workload identity | Which principals need access, and what exact policy scope is necessary? |
| Compute platform | What level of OS/runtime control and operational responsibility is required? |
| Data service | What access patterns, consistency, engine compatibility, RPO/RTO and cost apply? |
| Resilience | What failure domains are in scope and how is recovery tested? |
| Delivery | How are IaC, review, promotion, rollback and secrets governed? |
| Cost | What are the main usage drivers, owners, alerts and optimization measures? |

## 9. Production-readiness checklist
- [ ] Compartment model, ownership, tags and quotas are documented.
- [ ] IAM policies reviewed for least privilege and intended scope.
- [ ] Network flows and routing paths documented and validated.
- [ ] Secrets, keys, TLS and audit logging designed.
- [ ] SLOs, alarms, dashboards and incident runbooks exist.
- [ ] Capacity, quota and dependency-failure cases tested.
- [ ] Backups restored successfully and DR tested against RTO/RPO.
- [ ] Terraform plans, state, provider versions and change approvals controlled.
- [ ] Budget alerts, cost ownership and cleanup validated.

## Official references
- [OCI Architecture Center](https://www.oracle.com/cloud/architecture/)
- [OCI Well-Architected Framework](https://docs.oracle.com/en/solutions/oci-well-architected-framework/)
- [OCI Core Landing Zone](https://github.com/oci-landing-zones/oci-core-landingzone)
- [OCI IAM policies](https://docs.oracle.com/en-us/iaas/Content/Identity/Concepts/policies.htm)
- [OCI networking](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm)
