# Engineering Validation

**Query 1**: Confirm the PL (performance level) and category of each safety function according to EN ISO 13849 / AS/NZS 4024.1503 for the product(s) and system(s) listed. What PL and category are you creating, and when will this be accomplished?

**Response**: EN ISO 13849 - not yet compliant at present. AS/NZS 4024.1503 - not relevant.

* **Emergency Stop**: This feature is according to EN ISO 13849 since it obeys the following conditions:
  * Must stop hazardous movement safely
  * Must override all other functions and operations
  * Must remain in the stop position until reset manually
  * Design must prevent fault masking
* **Isolators**: According to the EN ISO 13849
* **Interlocks**: According to EN ISO 13849, it follows the below conditions:
  * Prevent access to moving or hazardous parts (e.g., robot, ASRS lifts, shuttle)
  * Prevent restart while a guard door is open
  * Stop motion immediately when a guard is breached.

**Query 2**: Confirm under an NDA that you would provide and that as part of an installation you would provide same-as-built details.

**Response**: Yes, under an NDA, we can provide it, as long as it does not create any issues with intellectual property.

**Query 3**: Provide details of the safety system functions, features, and methodologies.

**Response**: We currently provide several key safety features designed to enhance operator safety during operation:

* **Emergency Stop**: Our products are equipped with easily accessible emergency stop buttons that allow operators to immediately halt operations in case of an emergency.
* **Isolators**: We include isolators to ensure that the robot can be safely powered down when maintenance or servicing is required, reducing the risk of accidental activation.
* **Interlocks**: Our systems feature interlocks that prevent operation unless certain safety conditions are met, ensuring that the equipment cannot be used in unsafe situations. Interlock includes:
  * Prevents opening of the access door until the system is safe.
  * Locks gate while system is running; unlocks only after safe stop.
  * Prevents shuttle from entering zone during human access.
  * All safety interlocks are monitored in the PLC.
* **Added Guarding**: We incorporate additional guarding to protect operators from moving parts and other hazards, further enhancing safety during use.

These features work together to create a safe operating environment, allowing operators to interact with the equipment confidently.

**Query 4**: Provide details of all key components of the safety system.

**Response**: PLC, sensors, RCCB, MCBs, and tower lamp indicator.

**Query 5**: How is the safety system tested/validated for compliance with required standards and codes?

**Response**: Simulated alarms, comprehensive training drills, and automated API-level failure injection are essential components of our robust system testing strategy. These practices enable us to proactively identify vulnerabilities, ensure the effectiveness of our response protocols, and enhance the overall resilience of our infrastructure. By simulating alarm scenarios, we can assess the readiness of our teams in real-time situations. Conducting thorough drills allows us to refine our operational procedures, while automated API-level failure injection tests the robustness of our interfaces under stress, ensuring that we can maintain service continuity even in adverse conditions.

**Query 6**: How do you manage changes to any aspect of the safety system?

**Response**: Design review, quality check, and post-installation testing; periodic verification of efficacy. The majority of the components are CE certified.

**Query 7**: Specify the OEMs of key components such as motors, sensors, electrical components, etc.

**Response**: Motor & Drives- Fulling Motor\
PLC- Delta Electronics\
Sensor- Autonics\
MCBs- Schneider Electric\
Cables/Wires-Lapp & Polycab\
Terminal Blocks- Connectwell

**Query 8**: Confirm all guarding is in accordance with AS 4024?

**Response**: The guarding is an optional component and is a bespoke design for each customer.

**Query 9**: Floor, building, and environment interface specifications. Reference a recognized standard such as FM2.

**Response**: Indoor, secure, waterproof, level FLAT floor (i.e., a surface that is uniform and devoid of any significant slopes or irregularities), good lighting, no excessive humidity, and no excess dust. IS 2571, ASTM E1155.

**Query 10**: Electrical power requirements/consumption of product(s) and system(s) listed.

**Response**: The power requirements for the system are set at 220V AC, necessitating a reliable source of conditioned and uninterrupted power to ensure optimal performance. Each robot consumes approximately 1500 watts during active operation, allowing for efficient functionality. When not in use, the robots draw significantly less power, contributing to energy savings and reducing overall operational costs. This careful consideration of power consumption supports sustainability while maintaining the effectiveness of the system.

**Query 11**: Networks, data and communications requirements.

**Response**: The system utilizes an Ethernet-based internet connection that links to the main console hub, ensuring a stable and high-speed connection. This hub is equipped with a WiFi router, which facilitates seamless wireless communication among all remaining components of the system. This dual connectivity approach enhances overall reliability and flexibility, allowing devices to communicate effectively while maintaining optimal performance across the network.\
Wifi Standard- 802.11n (Wi-Fi 4)

**Query 12**: Provide details of the tote design. Is the tote design compliant with local standards and FM Global guidelines?

**Response**: Our system supports industry-standard totes sourced from customer-approved vendors, ensuring that they meet all necessary compliance standards. These totes can be easily procured and seamlessly integrated into the robot, allowing for efficient handling and transport of goods. By partnering with trusted suppliers, we guarantee that the materials used align with our commitment to quality and operational excellence, enhancing the overall effectiveness of our automated solutions. Our system supports the tote sizes 600mm length, 400mm width, and 80 to 240mm height.

**Query 13**: What is the range of product sizes that can go in the totes? What flexibility does the solution have for off-center center of gravity, handling products that have liquids in them, and dangerous goods such as aerosols?

**Response**: The system is designed to totes accommodate a diverse range of product sizes, making them highly versatile for various items typically found in a warehouse setting. While there is considerable flexibility in the dimensions of the items that can be stored, the only current restriction is a maximum weight limit of 20 kilograms per tote. This ensures safe handling while allowing for the efficient organization and storage of a wide array of products. As long as it is properly packed and contained and can be transported in accordance with local laws, we can handle it provided it meets our dimensional and weight requirements.

**Query 14**: Is the machine able to function in Australian temperature conditions?

**Response**: Not applicable. The robot is able to function within a wide range of ambient temperatures.
