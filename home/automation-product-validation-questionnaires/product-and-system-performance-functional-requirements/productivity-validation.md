# Productivity Validation

**Query 1**: How is throughput calculated? Provide a detailed explanation/worked example.

**Response**: The metric for the number of tote requests fulfilled per hour provides insight into operational efficiency and productivity within the fulfillment process. This figure reflects the volume of tote requests successfully processed within a given timeframe, serving as an indicator of the workflow's capacity and effectiveness.

Additionally, the average time required to retrieve any individual tote is a critical performance measure. It highlights the speed and efficiency with which items are located and accessed, offering valuable data for assessing overall operational performance. By monitoring both the number of fulfilled tote requests and the average retrieval time, we can identify areas for improvement, optimize resource allocation, and enhance the overall responsiveness of our fulfillment operations. This dual analysis not only aids in streamlining processes but also contributes to better inventory management and customer satisfaction.

**Query 2**: Is the throughput simulated? Is this done for the entire solution as well as each subsystem?

**Response**: Yes, in a digital twin simulator.

**Query 3**: How is the throughput simulated (i.e., what inputs, assumptions, constraints, and conditions are applied) for this subsystem? What are the activity details, e.g.order details, that are required for the simulation?

**Response**: Yes, various scenarios can be simulated via API-driven scripts. The digital twin can be leveraged to recreate.

**Query 4**: What testing/validation has been done to ensure accuracy of calculated/simulated results?

**Response**: Concurrent simulation & physical robot runs executing the same scripts can verify estimated results are accurate in reality.

**Query 5**: How are operational processes and inefficiencies accounted for in throughput calculations/simulations?

**Response**: The timings provided are end-to-end and incorporate all in-process admin functions and overheads.

**Query 6**: Are real-world conditions considered in throughput calculations/simulations?

**Response**: Yes.

**Query 7**: Is emulation included as part of the simulation?

**Response**: Yes.

**Query 8**: Is sensitivity analysis performed as part of the standard design process?

**Response**: We are conducting a sensitivity analysis on our system to evaluate how key performance metrics—such as retrieval time, throughput, and energy use—respond to changes in system parameters. By systematically varying inputs like robot speed, number of robots, bin dimensions, and control algorithms, we aim to identify the most influential factors affecting system efficiency. This analysis helps us prioritize design decisions, optimize system performance, and ensure robustness under varying operating conditions.

**Query 9**: What conditions and scenarios are typically considered when conducting sensitivity analysis?

**Response**: Tote sizes/loads/positions/request frequency.

**Query 10**: Of the throughputs provided, specify the type- mechanical, design, or operational.

**Response**: The throughput benchmarks we provided encompass all three levels—mechanical, design, and operational. Mechanical throughput is based on the physical limits of system components (e.g., robot speed, lift cycles) and is fully underwritten. Design throughput reflects expected performance under optimal layout and scheduling, supported by simulation, and is also underwritten. Operational throughput accounts for real-world conditions like maintenance and human interaction; we provide estimates for this, but underwriting is conditional on site validation and finalized workflows.

**Query 11**: Do you underwrite the performance of your solution to the as-proposed values? Which type is underwritten?

**Response**: Yes, we can underwrite the performance of our solution to the values proposed during the design and specification phase, provided that was requested as part of the commercial proposal, the system is installed, commissioned, and operated as intended. The types of performance parameters typically underwritten include

**Functional Performance**: The system will perform all specified control, monitoring, and reporting functions as described in the proposal and functional design documents.

**System Integration**: Interfaces with third-party systems and PLCs will function as defined, assuming compatible protocols and configurations.

**Response Times and Data Accuracy**: We guarantee performance levels such as data acquisition rates, alarm response times, and control loop timing within specified tolerances.

Any performance underwriting is subject to clearly defined boundary conditions and mutual agreement on scope, responsibilities, and testing protocols. Formal validation is typically confirmed through Factory Acceptance Testing (FAT) and/or Site Acceptance Testing (SAT).

**Query 12**: How do you manage underperformance of the contracted throughputs?

**Response**: Underperformance of contracted throughputs is managed through continuous monitoring via the control system, enabling early detection of any deviations from agreed targets. If a shortfall is identified, a root cause analysis is conducted to assess technical, operational, or process-related issues. This includes system diagnostics, review of input conditions, and engagement with relevant stakeholders to pinpoint the cause.

Corrective actions are then implemented, which may involve control logic adjustments, equipment recalibration, process changes, or operator training. If issues persist, escalation procedures outlined in the contract are followed, including potential retesting, warranty claims, or penalties. The focus remains on restoring performance quickly and sustainably, while applying lessons learned to prevent future issues.

