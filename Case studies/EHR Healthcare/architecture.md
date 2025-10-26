### 1. Describe the current technical environment of EHR Healthcare and explain the role of Kubernetes clusters in their architecture.

EHR Healthcare’s technical environment consists of software hosted in multiple colocation facilities. Their customer-facing applications are web-based and have recently been containerized, running on Kubernetes clusters. Data is stored in a mix of relational (MySQL, MS SQL Server) and NoSQL (Redis, MongoDB) databases. Legacy file- and API-based integrations with insurance providers are still hosted on-premises, and user management is handled via Microsoft Active Directory. Monitoring is performed using various open-source tools, but alerting is inconsistent and often ignored.

The role of Kubernetes clusters is central to their modernization efforts. By containerizing applications and orchestrating them with Kubernetes, EHR Healthcare can achieve:

* Consistent deployment and management of applications across environments.
* Improved scalability and resource utilization.
* Easier rollouts, rollbacks, and updates for applications.
* The ability to dynamically provision new environments for onboarding new providers or scaling for demand.
* Enhanced reliability and availability through self-healing and automated failover.
* Kubernetes thus forms the backbone of their application deployment strategy, enabling EHR Healthcare to meet their goals for scalability, agility, and operational efficiency.

### 2. How does EHR Healthcare plan to use Google Cloud to replace their current colocation facilities? Discuss the architectural changes involved.

EHR Healthcare is transitioning from traditional colocation facilities to Google Cloud to address scalability, disaster recovery, and deployment speed. This migration involves several architectural changes:

* **Infrastructure as a Service (IaaS) to Platform as a Service (PaaS):**
  - Instead of managing physical servers and networking in colocation centers, EHR Healthcare will leverage Google Cloud’s managed services, such as Google Kubernetes Engine (GKE) for container orchestration, Cloud SQL for managed relational databases, and Cloud Storage for scalable object storage.


* **Hybrid Connectivity:**
  - During the transition, EHR Healthcare must maintain secure, high-performance connections between on-premises systems (for legacy integrations) and Google Cloud. This is typically achieved using VPNs or dedicated interconnects, ensuring data flows securely and efficiently between environments.


* **Centralized Management and Monitoring:**
  - Google Cloud provides centralized tools for logging, monitoring, and alerting (e.g., Cloud Logging, Cloud Monitoring), replacing the fragmented open-source tools previously used. This centralization improves visibility, compliance, and proactive system management.


* **Automated Scaling and Provisioning:**
  - With Google Cloud, EHR Healthcare can dynamically scale resources based on demand, using features like autoscaling in GKE and managed instance groups. This is a significant shift from the static capacity planning required in colocation facilities.


* **Disaster Recovery and High Availability:**
  - Google Cloud’s global infrastructure allows for multi-region deployments, automated backups, and failover capabilities, enhancing disaster recovery and system availability compared to traditional colocation.


* **Security and Compliance:**
  - Google Cloud offers integrated security features (IAM, VPC Service Controls, encryption at rest and in transit) and compliance certifications, helping EHR Healthcare meet regulatory requirements more efficiently.


In summary, the move to Google Cloud transforms EHR Healthcare’s architecture from a manually managed, hardware-centric model to a cloud-native, automated, and scalable environment, supporting their growth and operational goals.


### 3. What are the key components of EHR Healthcare's existing software infrastructure, and how do they interact with each other?
Deeper Explanation:
EHR Healthcare’s software infrastructure is composed of several interconnected components, each serving a specific function within their service delivery:

- **Web-Based Customer-Facing Applications**: These are the primary interfaces used by medical offices, hospitals, and insurance providers. They have been containerized and are deployed on Kubernetes clusters, which manage scaling, deployment, and health of these applications.

- **Databases**: EHR Healthcare uses a mix of relational databases (MySQL, MS SQL Server) and NoSQL databases (Redis, MongoDB). The relational databases store structured data such as patient records, transactions, and user information, while NoSQL databases are used for caching, session management, and storing unstructured or semi-structured data.

- **Legacy Integrations**: Several file- and API-based integrations with insurance providers are still hosted on-premises. These systems facilitate data exchange between EHR Healthcare and external insurance systems, supporting claims processing, eligibility checks, and other business functions.

- **User Management**: Microsoft Active Directory is used for managing user identities and access control, ensuring that only authorized personnel can access sensitive systems and data.

- **Monitoring and Alerting Tools**: Various open-source tools are used for system monitoring and alerting, though the current setup is fragmented and not consistently acted upon.

**Interaction**:

* The web applications interact with the databases to retrieve and store data as users perform actions.
* When insurance-related operations are required, the applications communicate with the legacy integrations, which may involve secure connections to on-premises systems.
* User authentication and authorization are handled via Active Directory, ensuring secure access.
* Monitoring tools collect logs and metrics from all components, though improvements are needed for centralized visibility and proactive management.
* This interconnected infrastructure supports EHR Healthcare’s business operations but also presents challenges in scalability, monitoring, and integration—challenges that the migration to Google Cloud aims to address.
