### Architecture
**1. Describe the current technical environment of EHR Healthcare and explain the role of Kubernetes clusters in their architecture.**
EHR Healthcare operates web-based, customer-facing applications hosted in multiple colocation facilities. These applications have been containerized and are managed using Kubernetes clusters, which provide automated deployment, scaling, and management. Data is stored in a mix of relational (MySQL, MS SQL Server) and NoSQL (Redis, MongoDB) databases. Legacy integrations with insurance providers remain on-premises, and user management is handled via Microsoft Active Directory. Kubernetes enables consistent, scalable, and reliable application management, supporting rapid growth and operational efficiency.[1]

**2. How does EHR Healthcare plan to use Google Cloud to replace their current colocation facilities? Discuss the architectural changes involved.**
EHR Healthcare will migrate workloads to Google Cloud, leveraging managed services like GKE for containers, Cloud SQL for databases, and Cloud Storage for files. The architecture will shift from hardware-centric to cloud-native, with automated scaling, centralized monitoring, and improved disaster recovery. Secure hybrid connectivity (VPN or Dedicated Interconnect) will maintain links to legacy systems. This transition enables dynamic provisioning, high availability, and reduced operational overhead.[1]

**3. What are the key components of EHR Healthcare's existing software infrastructure, and how do they interact with each other?**
Key components include containerized web applications (on Kubernetes), relational and NoSQL databases, legacy on-premises integrations, Microsoft Active Directory for user management, and open-source monitoring tools. Applications interact with databases for data storage, use legacy integrations for insurance provider communication, and rely on Active Directory for authentication. Monitoring tools collect logs and metrics, though improvements are needed for centralized visibility.[1]

### Migration
**1. What are the primary challenges EHR Healthcare might face during the migration from colocation facilities to Google Cloud?**
Challenges include maintaining legacy system connectivity, ensuring data consistency and integrity during migration, minimizing downtime, meeting security and compliance requirements, establishing secure network connectivity, refactoring applications for cloud-native features, training staff, and setting up centralized monitoring.[1]

**2. Outline a high-level migration plan for EHR Healthcare to move their containerized applications to Google Cloud.**

1. Assess and inventory all workloads and dependencies.
2. Design the target Google Cloud architecture and set up GKE clusters.
3. Establish secure hybrid connectivity.
4. Pilot migration with a non-critical application.
5. Migrate databases using secure tools, ensuring data validation.
6. Gradually migrate applications using blue/green or canary deployments.
7. Test integrations and performance.
8. Set up centralized monitoring and optimize resources.
9. Complete cutover and decommission on-premises infrastructure.

**3. Discuss the steps EHR Healthcare should take to ensure minimal downtime during the migration process.**
Plan migrations during low-usage periods, use phased and incremental migration, implement blue/green or canary deployments, synchronize data between environments, prepare rollback procedures, maintain hybrid connectivity, conduct comprehensive testing, and set up real-time monitoring and support.[1]

### Security

**1. What security measures should EHR Healthcare implement to protect their data during and after the migration to Google Cloud?**
Encrypt data in transit and at rest, enforce least-privilege IAM policies, integrate with Active Directory, use VPCs and firewalls, enable audit logging, use DLP tools, ensure compliance with regulations, and use secure migration tools.[1]

**2. How can EHR Healthcare ensure secure and high-performance connections between their on-premises systems and Google Cloud?**
Use Dedicated Interconnect or VPN for secure, high-bandwidth connections; implement VPC peering and private access; enforce firewall rules; design for redundancy; monitor network performance; and audit access.[1]

**3. Discuss the role of Microsoft Active Directory in managing user access and how it can be integrated with Google Cloud for enhanced security.**
Active Directory provides centralized user management and authentication. Integration with Google Cloud via Cloud Identity or GCDS enables SSO, consistent access control, and enforcement of security policies across environments, supporting compliance and operational efficiency.[1]

### Scalability

**1. Explain how EHR Healthcare can leverage Google Cloud to dynamically scale and provision new environments.**
Use GKE autoscaling for containers, Managed Instance Groups for VMs, Infrastructure as Code for rapid environment provisioning, serverless services for event-driven workloads, and load balancing for traffic distribution. These enable rapid onboarding and cost-effective scaling.[1]

**2. What strategies can EHR Healthcare use to handle spikes in traffic and ensure consistent performance across their systems?**
Implement autoscaling, global load balancing, caching, CDN, rate limiting, real-time monitoring, decoupled architecture, and multi-region failover to maintain performance during traffic spikes.[1]

**3. How can EHR Healthcare maintain high availability (99.9%) for all customer-facing systems using Google Cloud?**
Deploy workloads across multiple regions/zones, use managed services with built-in redundancy, implement load balancing and health checks, enable autoscaling, set up disaster recovery, automate infrastructure, and monitor system health.[1]

### Compliance

**1. What steps should EHR Healthcare take to maintain regulatory compliance during and after their migration to Google Cloud?**
Identify applicable regulations, use compliant cloud services, encrypt data, enforce IAM and audit logging, ensure data residency, sign BAAs, monitor continuously, conduct security assessments, plan for incident response, and train staff.[1]

**2. Discuss the importance of centralized visibility and proactive action on system performance and usage in maintaining compliance.**
Centralized monitoring and logging enable detection of unauthorized access, support audit readiness, allow proactive issue resolution, enforce policies, simplify reporting, and support continuous improvement, all of which are essential for compliance.[1]

**3. How can EHR Healthcare ensure that their data storage and processing meet industry regulations and standards?**
Use compliant services, encrypt data, enforce access controls, enable audit logging, ensure data residency, conduct regular assessments, sign BAAs, plan for incident response, and train employees on compliance.
