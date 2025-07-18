# Technical Specifications

### Introduction

This document provides the detailed technical specifications for the Leapmile Nano warehousing platform designed to automate the storage and retrieval of items in a warehouse environment. The system supports both single-deep and double-deep bin storage configurations in racks, incorporates shuttles to move bins between locations, and interfaces with various automation elements such as conveyors and automated picking systems. The goal is to create a robust, efficient, and scalable solution that improves storage density, throughput, and overall warehouse operations.

This documentation provides the detailed technical specifications for the Leapmile Nano warehousing system, designed to optimize storage, retrieval, and throughput efficiency within a modern warehouse. The system includes advanced features for rack storage, shuttle operations, integration with other automation systems, and a centralized control platform with robust safety, security, and maintenance protocols.

### System Components

#### Rack Storage System

* **Rack Types:**
  * **Single Deep Storage**: A rack configuration where each slot holds a single bin.
  * **Double Deep Storage**: A rack configuration where each slot holds two bins (stacked back-to-back).
* **Material**: Racks are made of aluminium extrusion profiles, which is a material with a high strength-to-weight ratio, capable of supporting heavy loads and flexible deployment characteristics.
* **Height & Depth**: Customizable rack dimensions accommodate the required bin sizes and warehouse layout. Typical rack heights are \~3.3m.
* **Bin Slots**: Bins are designed for easy handling by shuttles. The system is able to handle bins with standard dimensions (e.g., 440mm x 640mm).
* **Weight Capacity**: Racks support a minimum weight of up to 20 kg per bin.
* **Rack Width**: Configurable for both single and double-deep racks to maximize space utilization.

### Shuttle System

* **Shuttle Types**:
  * Single Deep Shuttles: Used to retrieve and place bins in single deep storage slots.
  * Double Deep Shuttles: Specialized shuttles for retrieving bins from double deep storage locations. These support vertical movement (for bin stack retrieval) and horizontal travel across aisles.
* **Shuttle Motion**:
  * **Horizontal Movement**: Shuttles operate on high-precision tracks with smooth motion to minimize wear and friction. Tracks support speeds of up to 2 m/s.
  * **Vertical Movement**: Shuttles moving between double-deep racks have lifting and extension mechanisms to reach both front and rear bins, capable of vertical movements of up to \~3.3m.
  * **Drive Type**: Shuttles are equipped with electric drives (e.g., AC motors or DC motors (in the future may incorporate regenerative braking capabilities)) for high efficiency.
  * **Speed**: Shuttles operate at speeds of up to 1m/sec horizontally and 1m/sec vertically.
  * **Battery Power**: Shuttles are powered by a bus bar system with practically unlimited operating time.
  * **Communication**: Shuttles will communicate with the central control system via Wi-Fi or Ethernet for real-time status updates, task assignments, and error handling.

### Stations

#### Put Away Station

* **Functionality**: Operators or automated systems (e.g., conveyors) will deliver bins to the put-away station. The system will then assign an optimal storage location based on real-time data.
* **Interface with Shuttles**: The put-away station will interface with the shuttle system to place bins in either single or double-deep racks.
* **Put Away Optimization**: The system automatically chooses the most efficient rack location for put away, considering factors like available space and item popularity (frequent items placed in easily accessible locations).
* **Load Capacity**: Each station supports up to 25 kg of overall bin load (bin + contents).
* **Human-Machine Interface (HMI)**: Operators will be provided with a touchscreen interface to monitor put-away activities and, if needed, override the system.

### Pick Station

* **Functionality**: A pick station retrieves bins from the racks (via shuttles), and the operator picks items from the bins. It can also interface with automated picking systems (e.g., robotic arms).
* **Automatic Retrieval**: Shuttles automatically deliver bins to the pick station as part of the order fulfilment process.
* **Batch Picking**: Supports both single order picking and batch picking (retrieving multiple bins for multiple orders at once).
* **Integration with Pickers**: The pick station can interface with automated picking systems such as robotic arms or goods-to-person systems.
* **Load Capacity**: Pick stations support bins of various weights, with a maximum load of 25 kg/bin.

### 2.3.3 Transfer Station

* **Functionality**: The transfer station facilitates the movement of bins between different automation elements like conveyors, pickers, and the shuttle system.
* **Conveyor Integration**: The transfer station integrates seamlessly with conveyors to move bins in and out of the platform.
* **AGV Integration**: Bins can be transferred to and from the platform to external AGVs for further transport to other areas of the warehouse.
* **Capacity**: Each transfer station should handle a load of up to 25 kg/bin at a time.

### Conveyor System

#### Conveyor Types

* **Roller Conveyors**: Standard conveyors for moving bins between stations and transfer points.
* **Belt Conveyors**: Used for fragile or small items that require a gentle transport method.
* **Chain Conveyors**: For heavy-duty applications, used in areas where bins are too heavy for rollers.
* **Sortation Conveyors**: Automatic sorting of bins to the appropriate stations or destinations based on order requirements.

#### Conveyor Control

* **Speed Control**: Conveyors should have variable speed controls to match the flow rate of bins.
* **Integrated Sensors**: Conveyor systems will use barcode scanners, RFID readers, or vision systems to identify bins and track their locations throughout the system.
* **Load Capacity**: Conveyor systems should be able to carry bins with a load capacity of up to 25 kg/bin.

### Control System

#### Central Control System

* **Architecture**: The control system will have a distributed architecture consisting of a central server and local controllers for each system component (shuttles, racks, stations, AGVs, etc.).
* **Real-Time Data Processing**: The system must handle real-time data processing and decision-making to ensure smooth operations, including task assignment and error detection.
* **Task Scheduling**: The central system will schedule tasks (e.g., shuttle movements, AGV routing, put-away, and picking) based on priority, order requirements, and system performance.
* **Data Storage**: The system will use a SQL-based or NoSQL database to store bin locations, inventory data, and historical performance metrics.

#### Communication Network

* **Communication Protocols**: The system will use Ethernet/IP, Modbus TCP, and Wi-Fi for communication between system components.
* **Real-Time Communication**: Low-latency communication is required for real-time operations, ensuring timely shuttle movements, AGV coordination, and order fulfilment.

#### User Interface (HMI)

* **Operator Control Panel**: Touchscreen panels at various stations and control centers to monitor system status, execute manual interventions, and generate reports.
* **Alarm/Notification System:** Alerts will be sent to operators for system faults, jams, and error states through both visual (HMI) and audible notifications.
* **Mobile Integration**: Operators and warehouse managers can access system information remotely via mobile apps or web dashboards.

### Safety and Security

#### Safety Features

* **Emergency Stop**: Emergency stop buttons should be located throughout the warehouse for quick shutdown of all automated equipment.
* **Collision Avoidance**: The shuttle system and conveyors are equipped with sensors (e.g., ultrasonic, or infrared) to avoid collisions with other machines and human operators.
* **Safety Barriers**: Physical barriers are placed around high-traffic automated areas to ensure the safety of workers.

#### Security Features

* **Access Control**: Access to the control system and physical system components (e.g., maintenance panels, sensitive areas) is restricted with role-based authentication (e.g., OTP, RFID badges, biometric scans).
* **Data Encryption**: All system communication (including shuttles and stations) is encrypted using TLS or VPNs to protect data from external threats.
* **Audit Logs**: The system maintains an audit trail of actions performed by users and system events for security and traceability purposes.

### Maintenance and Support

#### Predictive Maintenance

* **Sensors and Diagnostics**: Critical components (shuttles, conveyors) can be equipped with vibration, temperature, and load sensors for predictive maintenance as required by clients.
* **Maintenance Alerts**: The system sends notifications for components that require maintenance based on sensor data analysis.

#### Support and Service

* Technical Support: customer support is available via phone, email, and remote diagnostics.
* Training: Operators, maintenance staff, and managers receive comprehensive training on the system’s operation and troubleshooting procedures.

### Integration with External Systems

#### WMS Integration

* The platform integrates with a Warehouse Management System (WMS) for order fulfilment, inventory management, and task prioritization.

#### ERP Integration

* The platform interfaces with Enterprise Resource Planning (ERP) systems to synchronize orders, stock levels, and financial transactions.

#### Robotics and Other Automation

* Integration with automated picking robots and goods-to-person systems will enhance picking efficiency by using the platform to automatically retrieve bins for robots to process.

\
