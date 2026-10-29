# OCI Enterprise Reference Architecture

## Scope
A conceptual Oracle Cloud Infrastructure architecture for learning and design review. Tailor to the workload threat model, data residency, regulatory needs, availability targets and cost objectives.

## Tenancy and governance
- Establish the tenancy and compartment hierarchy with ownership and lifecycle defined.
- Use OCI IAM policies with explicit compartment scopes. Use groups/dynamic groups and supported workload principals deliberately.
- Standardize tags, tag defaults, quotas, allowed regions, budgets and service guardrails.

## Identity and security
- Separate human and workload access.
- Use identity domains and federation appropriate to the identity model.
- Prefer instance principals/resource principals where supported instead of sharing long-lived credentials.
- Use OCI Vault for keys/secrets, Cloud Guard for security posture/detection, Security Zones where appropriate, and Audit for control-plane accountability.

## Networking foundation
- Avoid overlapping VCN CIDRs with on-premises and connected networks.
- Define VCNs, subnets, route tables, security lists and NSGs intentionally.
- Use Internet Gateway, NAT Gateway and Service Gateway only for the required flows.
- Use DRG for supported routed attachments; use LPG for appropriate VCN peering scenarios.
- Select FastConnect or Site-to-Site VPN based on connectivity, resilience, bandwidth and security needs.
- Document DNS, ingress/egress, private access and centralized inspection assumptions.

## Workload and data layers
- Choose Compute instances, instance pools/autoscaling, OKE or OCI Functions according to control and operations requirements.
- Use OCI Load Balancer/Network Load Balancer, WAF and certificates as appropriate.
- Choose Object Storage, Block Volume, File Storage Service and database services based on usage patterns, consistency, scale and recoverability.
- Use Events, Streaming, Queue, Notifications and Integration where the message/integration pattern fits.

## Delivery and operations
- Use Terraform with the OCI provider and/or OCI Resource Manager with protected state, pinned versions and reviewed plans.
- Use OCI DevOps where appropriate for build/deploy and rollout controls.
- Define Monitoring, Alarms, Logging, Logging Analytics, Audit, Cloud Advisor and budget visibility.
- Establish SLOs, runbooks, incident response, recovery drills and change controls.

## Resilience
- Determine availability-domain and fault-domain design based on the target region and service capabilities.
- Define RTO/RPO for each workload; choose backup, replication, warm standby or active approaches based on requirements.
- Test restoration/failover and document failback. A configured backup alone does not prove recoverability.

## Production-readiness checklist
- [ ] Compartment model, owners, tags and quotas documented.
- [ ] IAM policies reviewed for least privilege and scope.
- [ ] Network paths, gateways, routes and security rules documented.
- [ ] Secrets, keys, TLS and audit logging designed.
- [ ] SLOs, alarms, dashboards and incident runbooks exist.
- [ ] Capacity, quota and dependency-failure cases tested.
- [ ] Backups restored and DR tested against RTO/RPO.
- [ ] Terraform state, provider versions and change approvals controlled.
- [ ] Budgets, cost ownership and cleanup verified.

## Official references
- [OCI Architecture Center](https://www.oracle.com/cloud/architecture/)
- [OCI Well-Architected Framework](https://docs.oracle.com/en/solutions/oci-well-architected-framework/)
- [OCI Core Landing Zone](https://github.com/oci-landing-zones/oci-core-landingzone)
- [OCI IAM policies](https://docs.oracle.com/en-us/iaas/Content/Identity/Concepts/policies.htm)
- [OCI networking](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm)
