# Vendor System Architecture (WCS or Similar)

**Query 1**: What software dependencies does your system have?

**Response**: Python 3.X and its packages. All our software is open source and readily available.\
PLC: ISP software.

**Query 2**: Do you have one unified control system for multiple subsystems? If so, provide details/specifications.

**Response**: There is a single unified monitoring system. The rest of the systems are all running on the single robot computer instance.

**Query 3**: Describe standard control system architecture applicable to system/product(s).

**Response**: Interface contracts between service elements are REST API-based. All systems can run locally or in a distributed manner.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/system-architecture" %}

**Query 4**: Does the vendor use a single source code for their control system(s), or is it bespoke per project?

**Response**: Yes—Git repository.

**Query 5**: Please provide your software development life cycle.

**Response**: Development -> test -> staging -> production. Staging to production is prompted after peer reviews and code reads by the manager.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/software-development-life-cycle-sdlc" %}

**Query 6**: How do you ensure that software deployments remain up-to-date? And how do you ensure compatibility between versions for existing deployments? If you are using open-source code, how do you monitor and ensure you are uptodate?

**Response**: Unit and regression tests ensure compatibility is maintained. We rebuild systems periodically, and the build process includes patching to the latest/specified versions.

**Query 7**: Do you have plans for modification/customization of features, functions, dashboards, reports, etc.?

**Response**: Yes, we now provide support. We have made some modifications for the DHL HSR and Cochin robot installations, ensuring that the current workflow remains undisturbed as long as the requirements are met.

**Query 8**: Can you maintain DHL-specific code, standardized at a regional/global level? Who would own the IP if DHL has initiated and funded these?

**Response**: Yes, if required. By default all code and IP belong to the vendor unless explicitly scoped and carved out in writing via a special agreement.

**Query 9**: Can DHL-specific code be incorporated into major and minor releases without major modifications?

**Response**: Yes.

**Query 10**: What is the uptime/availability of the system(s) listed?

**Response**: We target 99.9% uptime, excluding planned service outages.

**Query 11**: Does the vendor have the capability for remote access for support and patching?

**Response**: Yes, when it's given internet access, we will be able to do remote support and patching.

**Query 12**: Is your system capable of operating in the cloud?

**Response**: Yes.

**Query 13**: Please describe your preferred solution delivery method.

**Response**: A combination of on-premise robotic systems and cloud infrastructure enables real-time health monitoring and diagnostics.

**Query 14**: Explain your preferred method for remote access (for maintenance/support).

**Response**: Secure SSH tunnels.

**Query 15**: What is the long-term supportability of any application, control system, OS, or similar?

**Response**: We ensure our platform is utilizing the latest stable OS and Python versions, which ensure no risk of abrupt end of life of support.

**Query 16**: Can you meet DHL Group standard SLAs relevant to the system(s) listed?

**Response**: Yes.

**Query 17**: Will ESCROW agreements be set up for all source code?

**Response**: Yes, escrow can be set up, but fees related to escrow deposits must be borne by the client.

**Query 18**: Please provide a sample functional specification similar to the system(s) listed.

**Response**:

{% embed url="https://docs.leapmile.com/home/product-documentation/functional-specifications" %}

**Query 19**: Describe a typical SIT plan for the product(s) and system(s) listed.

**Response**: The typical System Integration Testing (SIT) plan for our products and systems includes several key components to ensure comprehensive evaluation and validation. Here’s an overview of the process:

* **Objectives**: Define the goals of the SIT, including verifying that integrated components function as intended and meet specified requirements.
* **Test Scope**: Identify the specific products and systems to be tested, outlining their interactions and dependencies.
* **Test Environment**: Set up a controlled testing environment that closely resembles the production environment to ensure accurate results.
* **Test Cases**: Develop detailed test cases that cover various scenarios, including functional testing of integrated components. Performance testing to assess system responsiveness and stability under load. Security testing to identify any vulnerabilities.
* **Execution**: Conduct the tests according to the established plan, documenting results and any issues encountered during testing.
* **Defect Management**: Implement a process for tracking and resolving defects, ensuring that identified issues are addressed before moving to the next phase.
* **Reporting**: Compile and analyze test results, providing a comprehensive report that includes findings, recommendations, and any necessary follow-up actions.
* **Review and Sign-off**: Conduct a review with stakeholders to discuss the results and obtain formal sign-off on the SIT phase before proceeding to User Acceptance Testing (UAT) or deployment.

This structured approach to SIT helps ensure that our products and systems operate effectively when integrated, ultimately leading to successful implementation.&#x20;

**Query 20**: What disaster recovery capabilities does the vendor have in place? Please provide details.

**Response**: 4 working hours for a full rebuild is our target.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/rto-and-rpo-goals" %}

**Query 21**: Do you offer a dedicated TEST environment/channel as per DHL requirement?

**Response**: We offer digital twin simulation environments.

**Query 22**: Do you have emulation capability connected to the TEST environment?

**Response**: Yes.

**Query 23**: Provide details on how your system suits a multi-tenant facility, treating multiple clients as a single pool of tasks but retaining visibility of inventory, orders, tasks, etc. by client and also interfacing back to DHL by client.

**Response**: Our system can be configured to be multi-tenanted, multi-location, AND also be installed in single-tenant isolated mode per requirements.

**Query 24**: What is your position on future software modifications/improvements? Is there a strategic roadmap of improvements, and will DHL have access by default to future improvements?

**Response**: Yes, DHL will have access to all future releases subject to their systems being under active AMC contracts.

**Query 25**: Can the vendor provide the relevant IT infrastructure for the system(s) listed?

**Response**: Cloud instances for compute, managed cloud Postgres for database, and microservices for utility functionality.

**Query 26**: Is the vendor's controller(s)/WCS an in-house product or developed by a third party?

**Response**: None - we will integrate into DHL's existing systems.

**Query 27**: Is control system software supplied as part of the system(s)?

**Response**: Yes.

**Query 28**: Can you provide a functionality matrix?

**Response:** A functionality matrix will be provided at the next major release.





