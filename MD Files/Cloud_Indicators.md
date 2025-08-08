## Azure Well-Architected Framework Maturity Model Assessment

### Cost Optimization maturity evaluation

**Guidance:** Define cost-sharing processes and tools.
**Context:** Use collaboration tools to encourage cost optimization ideas across all team disciplines and define processes for sharing cost-saving ideas and knowledge.
**URL:** https://learn.microsoft.com/azure/well-architected/cost-management/maturity-model&tabs=level1#define-cost-sharing-processes-and-tools

**Guidance:** Gather detailed cost data from all sources.
**Context:** Explore all available tools and methods from your service provider to gather detailed cost data from all sources including invoiced and metered data.
**URL:** https://learn.microsoft.com/azure/well-architected/cost-management/maturity-model&tabs=level1#gather-detailed-cost-data-from-all-sources

**Guidance:** Determine cost drivers including noncloud factors.
**Context:** Identify how different workload components contribute to overall costs and determine cost drivers including processes and noncloud factors.
**URL:** https://learn.microsoft.com/azure/well-architected/cost-management/maturity-model&tabs=level1#determine-cost-drivers-including-non-cloud-factors

**Guidance:** Evaluate build versus buy decisions.
**Context:** Evaluate build versus buy decisions to optimize development costs considering control requirements, customization needs, and operational burden.
**URL:** https://learn.microsoft.com/azure/well-architected/cost-management/maturity-model&tabs=level1#evaluate-build-versus-buy-decisions

**Guidance:** Invest in team skills for cloud cost optimization.
**Context:** Invest in upskilling your team through training and certifications to enhance productivity and decision-making capabilities.
**URL:** https://learn.microsoft.com/azure/well-architected/cost-management/maturity-model&tabs=level1#invest-in-team-skills-for-cloud-cost-optimization

**Question:** How are you establishing team accountability and foundational processes for managing workload costs?
**Assessment Options:**
- We share financial goals, budget details, and workload spending with all stakeholders.
- We define processes and tools to share cost-saving ideas and knowledge.
- We gather detailed cost data, including invoiced and metered data, from all sources.
- We determine cost drivers including processes and noncloud factors.
- We evaluate build versus buy decisions to optimize development costs.
- We invest in our team's cloud cost optimization skills.
- Our strategy isn't listed above.

### Maturity level goal

**Guidance:** Not available
**URL:** https://learn.microsoft.com

**Question:** What level of architectural maturity would you like your workload to achieve?
**Assessment Options:**
- We want to establish a solid foundation on Azure.
- We want to build workload assets and address technical challenges.
- We want to be production-ready and involve business stakeholders in decisions.
- We want to learn from production and maintain stability.
- We want to future-proof our solution by implementing agility and innovation.

### Operational Excellence maturity evaluation

**Guidance:** Adopt standard collaboration methodologies and tools.
**Context:** Begin with industry-proven tools and software development life cycle (SDLC) processes like Agile, Scrum, and Kanban boards to enhance development efficiency. Use established industry standards that experienced developers are familiar with to minimize learning curves.
**URL:** https://learn.microsoft.com/azure/well-architected/operational-excellence/maturity-model&tabs=level1#adopt-standard-collaboration-methodologies-and-tools

**Guidance:** Set up source control processes.
**Context:** Select appropriate source control technology and establish processes to ensure that team members don't interfere with each other's work. Structure source code based on application scale with clearly defined interfaces for component discoverability.
**URL:** https://learn.microsoft.com/azure/well-architected/operational-excellence/maturity-model&tabs=level1#set-up-source-control-processes

**Guidance:** Use infrastructure as code (IaC) as your primary deployment approach.
**Context:** Use a declarative approach as the standard for deployments to ensure consistency, repeatability, and long-term benefits like automation and self-documentation. Start with Azure-native tools like Bicep and Terraform.
**URL:** https://learn.microsoft.com/azure/well-architected/operational-excellence/maturity-model&tabs=level1#use-infrastructure-as-code-iac-as-your-primary-deployment-approach

**Guidance:** Prioritize security from the start.
**Context:** Prioritize security even at early stages by acknowledging complexities from segmentation requirements and building security measures into foundations. Make tools and processes transparent for vulnerability detection through audits.
**URL:** https://learn.microsoft.com/azure/well-architected/operational-excellence/maturity-model&tabs=level1#prioritize-security-from-the-start

**Question:** How are you emphasizing teamwork and unity to establish a strong operational foundation?
**Assessment Options:**
- We encourage collaboration and foster a blameless culture for unified problem-solving.
- We adopt standard collaboration methodologies and tools to enhance development efficiency.
- We set up source control processes to manage team coordination effectively.
- We use infrastructure as code (IaC) as our primary deployment approach for consistency.
- We prioritize security from the start to build comprehensive protection.
- Our strategy isn't listed above.

### Performance Efficiency maturity evaluation

**Guidance:** Choose appropriate networking resources.
**Context:** Assess network needs to determine appropriate services and configurations considering traffic, bandwidth, latency, and throughput. Use private virtual networks and load balancing services to reduce latency and distribute traffic effectively.
**URL:** https://learn.microsoft.com/azure/well-architected/performance-efficiency/maturity-model&tabs=level1#choose-appropriate-networking-resources

**Guidance:** Choose appropriate compute resources.
**Context:** Assess compute needs including instance type, scalability, and service tiers. Consider containerization for performance gains through isolation and resource efficiency while choosing scalable compute services.
**URL:** https://learn.microsoft.com/azure/well-architected/performance-efficiency/maturity-model&tabs=level1#choose-appropriate-compute-resources

**Guidance:** Choose appropriate data store services.
**Context:** Select data storage solutions that align with your performance requirements and access patterns. Consider factors like data volume, query complexity, and consistency requirements to optimize data store performance.
**URL:** https://learn.microsoft.com/azure/well-architected/performance-efficiency/maturity-model&tabs=level1#choose-appropriate-data-store-services

**Question:** How are you establishing performance expectations and selecting appropriate components?
**Assessment Options:**
- We gather comprehensive requirements and define clear performance targets.
- We select appropriate networking resources for our performance requirements.
- We select compute resources that align with our workload's performance needs.
- We select data store services optimized for our access patterns and performance needs.
- Our strategy isn't listed above.

### Reliability maturity evaluation

**Guidance:** Identify critical user flows and system flows to prioritize reliability efforts.
**Context:** Break down your workload into user flows and system flows to create a catalog for prioritization. This foundation helps inform conversations with business stakeholders about the most critical components.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#identify-the-critical-user-and-system-flows

**Guidance:** Select the right design model, resources, and features.
**Context:** Apply strategic selection at architecture, Azure services, and SKU levels to ensure that components meet current needs while remaining flexible for evolution. Choose cloud-native services that enhance availability through simple configurations.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#select-the-right-design-model-resources-and-features

**Guidance:** Deploy with a basic level of redundancy.
**Context:** Create multiple instances for redundancy, preferably by using zone redundancy to spread instances across multiple Azure datacenters. This practice eliminates single points of failure with immediate reliability improvements.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#deploy-with-a-basic-level-of-redundancy

**Guidance:** Enable metrics, logs, and traces to monitor flows.
**Context:** Use platform-native tools like Azure Monitor to ensure visibility across your workload with built-in alerting capabilities. This foundational observability enables understanding of baseline performance and anomaly identification.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#enable-metrics-logs-and-traces-to-monitor-flows

**Guidance:** Start building a failure mitigation playbook.
**Context:** Document potential platform-level failures, their associated risks, and mitigation strategies as a living document. This systematic approach helps your team understand failure scenarios and prepare structured responses.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#start-building-a-failure-mitigation-playbook

**Guidance:** Add mechanisms to recover from transient failures.
**Context:** Use built-in SDKs and configurations to handle transient faults and keep your system active during common cloud failures. Implement proven patterns like retry logic and circuit breakers for immediate resilience benefits.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#add-mechanisms-to-recover-from-transient-failures

**Guidance:** Run basic reliability tests integrated into your development life cycle.
**Context:** Integrate basic reliability testing early in the software development life cycle, starting with unit tests to validate functionality and configurations. This proactive approach helps identify problems when they're easier to fix.
**URL:** https://learn.microsoft.com/azure/well-architected/reliability/maturity-model&tabs=level1#run-basic-tests

**Question:** How are you establishing solid groundwork for resiliency in your workload?
**Assessment Options:**
- We evaluate opportunities to offload operational responsibility.
- We identify critical user flows and system flows.
- We select the right design models, resources, and features for our architecture.
- We deploy with a basic level of redundancy.
- We enable metrics, logs, and traces to monitor our critical flows.
- We build a failure mitigation playbook.
- We add mechanisms to recover from transient failures by using built-in patterns.
- We run basic reliability tests.
- Our strategy isn't listed above.

### Security maturity evaluation

**Guidance:** Externalize identity and access management to an identity provider (IdP).
**Context:** Use an identity provider like Microsoft Entra ID to maintain security standards by controlling access to workload components and using nonhuman identities. This practice enhances security through multifactor authentication and detailed access logs.
**URL:** https://learn.microsoft.com/azure/well-architected/security/maturity-model&tabs=level1#externalize-identity-and-access-management-to-an-identity-provider-idp

**Guidance:** Observe access patterns of key identities, and apply an appropriate level of security.
**Context:** Observe access behaviors across workload teams to determine appropriate access levels and identify opportunities to replace human access with managed identities. Standardize just-in-time access for sensitive resources.
**URL:** https://learn.microsoft.com/azure/well-architected/security/maturity-model&tabs=level1#observe-access-patterns-of-key-identities-and-apply-an-appropriate-level-of-security

**Guidance:** Encrypt data at rest.
**Context:** Secure data at rest to ensure confidentiality and integrity through strong encryption and strict access controls. Configure encryption on VM disks, storage accounts, and databases by using built-in mechanisms.
**URL:** https://learn.microsoft.com/azure/well-architected/security/maturity-model&tabs=level1#encrypt-data-at-rest

**Guidance:** Encrypt data in transit.
**Context:** Secure data in transit to protect from attackers who might intercept data during transmission. Use TLS 1.2 as the default version for all systems and avoid weaker cipher suites.
**URL:** https://learn.microsoft.com/azure/well-architected/security/maturity-model&tabs=level1#encrypt-data-in-transit

**Guidance:** Protect application secrets.
**Context:** Properly manage application secrets including passwords, API keys, and certificates to prevent data breaches and service disruption. Use solutions like Azure Key Vault to manage secrets securely.
**URL:** https://learn.microsoft.com/azure/well-architected/security/maturity-model&tabs=level1#protect-application-secrets

**Question:** How are you establishing a minimum viable security posture as your foundation?
**Assessment Options:**
- We integrate baseline security into our software development life cycle (SDLC) phases.
- We externalize identity and access management to an identity provider.
- We observe access patterns of key identities and apply appropriate security levels.
- We encrypt data at rest to ensure confidentiality and integrity.
- We encrypt data in transit by using modern protocols and secure configurations.
- We protect application secrets by using secure management solutions.
- Our strategy isn't listed above.

---
## Cloud Adoption Strategy Evaluator

### Creating your business case

**Guidance:** Review the key components of a business case.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/cloud-migration-business-case

**Guidance:** Learn how to build a digital transformation timeline.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/digital-transformation-timeline

**Question:** Creating a business case
**Assessment Options:**
- Do you understand the key components of building a business case?
- Do you know how to build a digital transformation timeline?

### Documenting business outcomes you expect

**Guidance:** The most successful transformation journeys start with a business outcome in mind. Learn more about business outcomes.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/business-outcomes

**Guidance:** Learn more about business outcomes and the business outcome template.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/business-outcomes

**Question:** What are the business outcomes driving your cloud transformation?
**Assessment Options:**
- Increase profitability while driving compliance
- Accelerate sales, improve customer lifetime value
- Acquire and retain customers, build a reputation
- Retain, recruit, and empower employees
- Meet market growth requirements and environmental sustainability metrics
- Global reach
- Performance and reliability
- None of the above

**Question:** Do these outcomes have associated business drivers, KPIs, and necessary technical capabilities?
**Assessment Options:**
- Yes
- No
- Don't know

### Financial considerations for you to evaluate

**Guidance:** Create a financial model for cloud transformation.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/financial-models

**Guidance:** Understand cloud accounting.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/cloud-accounting

**Question:** Have you developed a financial model or performed an economic assessment that provides business justification for moving to the cloud?
**Assessment Options:**
- Yes
- No
- Don't know

**Question:** It's important to understand how to account for cloud costs before you begin a cloud transformation journey. Select your company's model from the following common cloud accounting models.
**Assessment Options:**
- Cost-center model
- Profit-center model
- Charge-back model
- Showback or awareness-back model
- Don't know
- None of the above

### Identifying your motivations

**Guidance:** When responding to a critical business event that drives cloud adoption, review the get started guide for accelerating migration.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/get-started/migrate

**Guidance:** Understand the critical events that can drive motivations for cloud adoption.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/motivations

**Guidance:** Review the cloud center of excellence guidance.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/organize/cloud-center-of-excellence

**Guidance:** Review examples of cloud adoption plans with four horizons.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/digital-transformation-timeline

**Question:** How would you describe your cloud strategy?
**Assessment Options:**
- Developed as necessary, fragmented
- Clear and defined
- Transformational and innovative
- Requires optimization

**Question:** Are you responding to any critical business events, such as, datacenter exit, mergers and acquisition, end of support for mission-critical technologies, or response to regulatory compliance change?
**Assessment Options:**
- Yes
- No

**Question:** What are the top three motivations for your cloud adoption? (Select up to three)
**Assessment Options:**
- Reduce capital expense
- Improve cost efficiency
- Increase business agility
- Improve internal operations or processes
- Prepare for new technical capabilities
- Scale to meet market demands
- Scale to meet geographic demands
- Improve customer experience and engagement
- Transform products or services
- None of the above

---
## Strategic Migration Assessment and Readiness Tool

### Business case

**Guidance:** Build a cloud migration business case.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/cloud-migration-business-case

### Business strategy

**Guidance:** Align stakeholders on a cloud adoption strategy.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/define-strategy

### Cloud adoption plan

**Guidance:** Build a cloud adoption plan that balances the portfolio and aligns to business outcomes.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/plan

### Financial outcomes

**Guidance:** Plan for the financial outcomes of cloud adoption.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/financial-models

### Motivations

**Guidance:** Understand motivations for cloud adoption.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/motivations

### Partner alignment

**Guidance:** Evaluate partner support options for your migration.
**URL:** https://azure.microsoft.com/migration/partners

### Stakeholders

**Guidance:** Define and align stakeholders to your cloud adoption strategy.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/organize/get-started

### Technical outcomes

**Guidance:** Align business, people, and technology readiness to cloud adoption.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/readiness

---
## FinOps Review

### Section 1: Introduction

**Guidance:** Set up a FinOps team in your organization.
**URL:** https://learn.microsoft.com/training/modules/get-started-with-finops/3-finops-team-members-and-personas

**Guidance:** Complete this statement: The most important goal for our organization's FinOps journey is to ___.
**URL:** https://learn.microsoft.com/assessments/finops/

### Section 2: Manage the FinOps Practice

**Guidance:** FinOps Practice Operations
**Context:** Start by forming a dedicated FinOps team (members that are passionate about FinOps, Cost Optimization, efficiency) and defining clear roles and responsibilities. Implement training sessions and workshops to enhance cost-awareness and collaboration.
**URL:** https://learn.microsoft.com/training/modules/get-started-with-finops/

**Guidance:** Policy & Governance
**Context:** Begin your governance journey with a small set of foundational policies that cover cost allocation, resource tagging, and budget alerting. This establishes a baseline for accountability and visibility.
**URL:** https://learn.microsoft.com/cloud-computing/finops/framework/manage/governance

### Section 3: Understand Usage & Cost

**Guidance:** Anomaly Detection
**Context:** Begin with Azure's built-in anomaly detection features. Set up basic alerts for your primary subscriptions to get notified of any unusual spending patterns. This is a simple yet effective first step towards proactive cost management.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/understand/analyze-unexpected-charges

**Guidance:** Cost Allocation & Budgets
**Context:** Start with a simple and clear tagging strategy for your key resources and applications. This will enable better cost allocation and visibility. Additionally, set up initial budgets for your main departments or projects to foster accountability and prevent overspending.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/cost-mgt-best-practices

**Guidance:** Reporting & Visualization
**Context:** Start by exploring the built-in reporting features of your cloud provider, like Azure Cost Management. Create a basic dashboard to track your top-spending services and resource groups. This provides immediate visibility and helps you identify potential areas for optimization.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/quick-acm-cost-analysis

### Section 4: Track performance & measure progress

**Guidance:** Establishing & measuring KPIs
**Context:** Begin by defining a few key performance indicators (KPIs) that are most relevant to your organization's goals, such as 'Cost per transaction' or 'Resource utilization rate.' This provides a clear focus for your optimization efforts.
**URL:** https://learn.microsoft.com/cloud-computing/finops/framework/measure-progress/

**Guidance:** Tracking against baselines, budgets, and forecasts
**Context:** Start by setting a baseline for your current cloud spending and create initial budgets for your main projects or departments. This will provide a clear reference point for tracking your progress and identifying variances.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-create-budgets

### Section 5: Optimize for cloud

**Guidance:** Cloud Rate Optimization
**Context:** Begin by reviewing your current resource usage and identifying opportunities to leverage Azure Hybrid Benefit for your existing licenses. Also, explore Azure Reservations for your steady-state workloads to get significant cost savings.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/cost-mgt-best-practices

**Guidance:** Resource Utilization & Efficiency
**Context:** Start by identifying and deleting unused resources, like unattached disks or idle virtual machines. This is a simple yet effective way to reduce waste and optimize costs.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/tutorial-optimize-costs-recommendations

---
## Cloud Governance

### Build a cloud governance team

**Guidance:** Select the members of your cloud governance team.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/build-cloud-governance-team#select-the-members-of-the-cloud-governance-team

**Guidance:** Define the functions of your cloud governance team.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/build-cloud-governance-team#define-the-functions-of-the-cloud-governance-team

**Guidance:** The cloud governance team should meet regularly to review policies and ensure compliance. How often does your team meet?
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/build-cloud-governance-team

### Define cloud policy

**Guidance:** Create a corporate policy for cloud adoption.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/policy-compliance/corporate-policy

**Guidance:** Ensure that your cloud policies are well-defined and communicated to all stakeholders.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/policy-compliance/corporate-policy

### Manage costs

**Guidance:** Implement cost management policies.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/cost-management

**Guidance:** Use cost management tools to monitor and control cloud spending.
**URL:** https://learn.microsoft.com/azure/cost-management-billing/costs/

### Secure the cloud

**Guidance:** Implement security baseline policies.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/security-baseline

**Guidance:** Use security tools to protect your cloud resources.
**URL:** https://azure.microsoft.com/services/security-center/

---
## Cloud Journey Tracker

### Governance

**Guidance:** Build a governance team.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/build-cloud-governance-team

**Guidance:** Create a governance MVP.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/governance-mvp

### Plan

**Guidance:** Learn how to build a cloud adoption plan.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/plan

**Guidance:** Build a business justification.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/strategy/cloud-migration-business-case

### Ready

**Guidance:** Choose a landing zone.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone

**Guidance:** Set up your first landing zone.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/ready

### Strategy

**Guidance:** Use the Azure pricing calculator.
**URL:** https://azure.microsoft.com/pricing/calculator

**Guidance:** Learn about architecting an environment in the cloud.
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework

---
## Cloud Adoption Security Review

### Business Alignment

**Guidance:** Develop or improve the Security Baseline discipline
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/govern/security-baseline/discipline-improvement

**Guidance:** Establish team for identity and key management functions
**URL:** https://learn.microsoft.com/azure/cloud-adoption-framework/organize/cloud-security-identity-keys

**Question:** Rank your security program's business alignment
**Assessment Options:**
- Ad-hoc & Disconnected (Security decisions made in isolation)
- Business Informed (Security program has visibility into business goals)
- Business Aligned (Security strategy is aligned with business goals)
- Business Partner (Security is a key partner in achieving business goals)

### Security Operations

**Guidance:** Only grant access to privileged roles for as long as they are needed to perform the immediate task
**URL:** https://learn.microsoft.com/insidetrack/implementing-a-zero-trust-security-model-at-microsoft

**Guidance:** Use Microsoft Entra ID reporting capabilities to generate access control audit reports
**URL:** https://learn.microsoft.com/insidetrack/implementing-a-zero-trust-security-model-at-microsoft
