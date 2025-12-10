DevOps is the combination of cultural philosophies, practices, and tools that increases an organization’s ability to deliver applications and services at high velocity: evolving and improving products at a faster pace than organizations using traditional software development and infrastructure management processes. This speed enables organizations to better serve their customers and compete more effectively in the market.

> Under a DevOps model, development and operations teams are no longer “siloed.” Sometimes, these two teams are **merged into a single team** where the **engineers work across the entire application lifecycle**, from development and test to deployment to operations, and develop a range of skills not limited to a single function.

The hallmarks of DevOps are [[Continuous Integration (CI)]] and [[Continuous Delivery]] (CI/CD), which support smaller, faster software updates. With CI/CD, small chunks of new code are merged into the code base at frequent intervals, and then automatically integrated, tested and prepared for deployment to the production environment.

DevOps is an evolution of the [agile software development](https://www.ibm.com/think/topics/agile-vs-waterfall) methodology, which emerged as an alternative to the waterfall methodology. In the waterfall approach, software development teams spent months developing large bodies of code, which then underwent months of testing before release. In contrast, agile development takes an iterative approach to the software delivery lifecycle.  
  
DevOps adds new processes and tools to the agile methodology, notably the [automation](https://www.ibm.com/think/topics/automation) of much of the CI/CD pipeline.

## The DevOps lifecycle

The DevOps lifecycle is designed to optimize the rapid delivery of high-quality software. It includes a series of iterative, automated workflows that run within a larger automated and iterative development lifecycle.

![[Pasted image 20251210170616.png]]

### 1. Planning

First, teams scope out new features and functions for the next release. During this workflow, they draw on user feedback, case studies and inputs from internal stakeholders such as platform and infrastructure engineers, security, compliance, governance, [risk management](https://www.ibm.com/think/topics/risk-management) and line-of-business teams.

The goal of the planning stage is to create a backlog document. The backlog is a prioritized list of new features, improvements and bug fixes that will be added to the product over time.

### 2. Coding

The DevOps team codes the new and enhanced features identified in the backlog. Common coding practices in DevOps include:

- **Test-driven development (TDD):** Developers first create tests that the code must pass before they write the code itself.      
- **Pair programming:** Two programmers collaborate at the same workstation, with one programmer writing the code and the other evaluating the code.     
- **Peer code reviews**: Members of the development team review each other’s code for bugs, errors or areas for improvement.

Developers often use their local workstations to write and test code before sending it down to the next stage of the continuous delivery pipeline.

### 3.  Building

New code is integrated into the existing code base, then tested and packaged for release and deployment. Activities that are often automated at this stage include merging code changes into a master copy; placing the updated code into a repository; and compiling, testing and packaging code into an executable file.  
  
In DevOps, the output of the build phase is often stored in a binary repository. Unlike a source code repository, a binary repository stores packaged outputs, such as libraries and executable files, to be reused in other phases of the development lifecycle.

### 4. Testing

DevOps teams use testing, typically automated testing, to make sure that the updated application meets appropriate standards and requirements.

The classical DevOps approach includes a discrete test phase that occurs between building and release. However, DevOps has advanced such that certain elements of testing can occur throughout the process. Unit tests—tests of small pieces of code in isolation—might run during the coding phase. After integrating new code, linting programs might analyze it for errors.  
  
[Continuous testing](https://www.ibm.com/think/topics/continuous-testing) helps implement the principle of [shift-left testing](https://www.ibm.com/think/topics/shift-left-testing), a software development approach that emphasizes moving testing activities earlier in the development process. This approach helps organizations identify problems sooner and remediate them more effectively. 

### 5. Release

The release stage is the last workflow before users access the application. This stage includes a series of final tests to ensure that the software meets quality, compliance and security standards and is ready for external use.

If errors or defects are found, the team has a chance to intercept and remediate any problems before users see them. When all issues are fixed and the application meets all requirements, it can be released to the production environment. In most DevOps pipelines, this process is largely automated.

The release stage might also involve the provisioning of infrastructure components such as servers, [databases](https://www.ibm.com/think/topics/infrastructure-as-code) and [load balancers](https://www.ibm.com/think/topics/load-balancing). DevOps often uses [infrastructure as code](https://www.ibm.com/think/topics/infrastructure-as-code) to automate this process. 

### 6. Deploy

At this stage, the project moves to a production environment where users can access the updated application.

Many organizations deploy first to a subset of end users to ensure that the application works properly. When stability is established, the application can be deployed to everyone.

### 7. Operate

In this stage, DevOps teams check that new features are running smoothly and are available to users with no interruptions in service. They use automated observability and management tools to continuously monitor and optimize operations to make sure that network, storage, platform, compute and [security postures](https://www.ibm.com/think/topics/security-posture) are all working properly.

### 8. Monitor

In this stage, teams collect and analyze feedback from users and lessons from previous workflows to help improve processes and products going forward. This continuous monitoring of features, functions, performance and business value informs the planning for the next release of new features and enhancements.

### References
https://aws.amazon.com/devops/what-is-devops/
https://www.ibm.com/think/topics/devops

---

## 2. Core DevOps Principles

- Automation
- Continuous feedback
- Shared ownership
- Reliability and resilience
- Infrastructure as code
- Security by design (DevSecOps)

---

## 3. Source Control & Collaboration

- Git fundamentals
- Branching strategies
- Pull requests and code reviews
- Monorepo vs multirepo
- Trunk-based development

---

## 4. [[Continuous Integration (CI)]]

- Build automation
- Dependency management
- Automated testing
- Static code analysis
- CI pipeline design

---

## 5. Continuous Delivery & Deployment (CD)

- Deployment automation
    
- Release orchestration
    
- Environment promotion
    
- Rollback strategies
    
- Progressive delivery
    

---

## 6. Deployment Strategies

- Rolling updates
    
- Blue-green deployments
    
- Canary releases
    
- Feature flags
    

---

## 7. Infrastructure as Code (IaC)

- Declarative vs imperative IaC
    
- Terraform, Pulumi, CloudFormation
    
- Configuration management (Ansible, Chef)
    
- State management and drift detection
    

---

## 8. Containerization & Orchestration

- Docker fundamentals
    
- Image registries
    
- Kubernetes architecture
    
- Helm and operators
    
- Service meshes
    

---

## 9. Cloud & Platform Services

- IaaS, PaaS, SaaS
    
- Networking basics (VPC, load balancing)
    
- Storage and databases
    
- Identity and access management (IAM)
    

---

## 10. Observability & Reliability

- Logging
    
- Metrics and monitoring
    
- Distributed tracing
    
- SLIs, SLOs, SLAs
    
- Incident response
    

---

## 11. DevSecOps

- Secrets management
    
- Dependency vulnerability scanning
    
- Static and dynamic security testing
    
- Image scanning
    
- Zero-trust principles
    

---

## 12. Environment & Configuration Management

- Environment parity
    
- Secrets vs config
    
- Feature toggles
    
- Ephemeral environments
    

---

## 13. Release & Change Management

- Semantic versioning
    
- Change approvals and automation
    
- Release notes generation
    
- Audit trails and compliance
    

---

## 14. Pipeline Performance & Optimization

- Pipeline as code
    
- Parallelization
    
- Build caching
    
- Test optimization
    
- DORA metrics
    

---

## 15. Cost & Resource Optimization (FinOps)

- Autoscaling
    
- Resource right-sizing
    
- Cost visibility
    
- Budget enforcement
    

---

## 16. Governance, Risk & Compliance

- RBAC
    
- Policy as code (OPA)
    
- Compliance automation
    
- Supply chain security
    

---

## 17. DevOps Toolchain

- CI/CD platforms
    
- IaC tools
    
- Observability stack
    
- Security tools
    

---

## 18. Organizational Models

- Embedded DevOps
    
- Central DevOps teams
    
- Platform Engineering overlap
    
- SRE integration
    

---

## 19. DevOps Maturity Models

- Ad-hoc → Managed → Optimized
    
- DORA capability model
    
- CALMS framework
    

---

## 20. Future Trends

- GitOps
    
- Platform Engineering
    
- AIOps
    
- Serverless CI/CD