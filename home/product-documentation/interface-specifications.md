# Interface Specifications

This document provides detailed interface specifications for the Leapmile Nano warehousing platform, which includes components such as rack storage, shuttles, put-away/pick stations, conveyors, AGVs, and integration with other automation systems. The document describes communication protocols, system interfaces, data exchange formats, and reporting standards required for effective integration, monitoring, and operation.

#### The interfaces described here are designed to facilitate:

* **Communication** between the system and other automation elements (e.g., shuttles, conveyors, picking systems, etc.).
* **Data exchange** between the platform and external systems (e.g., Warehouse Management System (WMS), Enterprise Resource Planning (ERP) systems), Cloud databases, and API Servers.
* **Reporting and data** retrieval in various formats (CSV, PDF, HTML).
* **Control and monitoring** via APIs, including real-time data transmission.

#### The platform includes several key components:

* **Rack Storage System**: Racks for storing bins in single or double deep configurations.
* **Shuttle System**: Automated vehicles that transport bins between storage locations and stations.
* **Put away and Pick Stations**: Stations for storing and retrieving bins from racks.
* **Conveyors**: Transporting bins between various system components.
* **Control and Monitoring System**: The central control system for managing all automated components, tracking bin locations, and overseeing system performance.

The platform supports a variety of communication protocols for different layers of interaction, including secure communication, data exchange, and automation control.

### SSL/HTTPS Communication

* **Purpose**: Secure data transmission between system components (e.g., control systems, web-based user interfaces, APIs).
* **Standards:**
  * SSL/TLS encryption for all data exchanges.
  * HTTPS for secure web-based interactions (e.g., operator dashboards, system status monitoring).
  * Certificate-Based Authentication for ensuring the integrity and authenticity of the communication.
* **Ports:**
  * Standard HTTPS port: 443.
  * Custom ports may be required based on the infrastructure setup.

### REST APIs

* **Purpose**: Enable integration with external systems such as WMS, ERP, and third-party automation platforms.
* **Protocol**: RESTful APIs, using HTTP/HTTPS for communication.
* **Authentication**: JWT, OAuth 2.0 or API Keys for secure API access.
* **Data Format**: JSON for data exchange.
* **Endpoints**: A variety of RESTful endpoints will be exposed, each designed to interact with specific system components (e.g., shuttle movements, bin retrieval, system status).&#x20;
  * **Example Endpoint**: GET /api/shuttle/status (Returns current status of all shuttles).
  * **Example Endpoint**: POST /api/putaway (Initiates a putaway operation).
  * **Example Endpoint**: GET /api/order/status/{order\_id} (Fetches the current status of an order in the system).
* **Error Handling**: Standardized HTTP status codes (e.g., 200 OK, 404 Not Found, 500 Internal Server Error) and detailed error messages in the response body.

### Modbus Communication (for hardware integration)

* **Purpose**: Interface with industrial automation hardware such as conveyors, sensors, and actuators.
* **Protocol**: Modbus TCP/IP for communication between the control system and physical hardware.
* **Communication Parameters:**
  * **Slave ID**: Unique identification for each hardware component (e.g., each shuttle, conveyor motor, or sensor).
  * **Function Codes**: Standard Modbus function codes (e.g., FC03 for reading holding registers, FC06 for writing to a register).
  * **Data Format**: Data will be exchanged in a binary format, with payloads encoded as Modbus registers.
  * **Error Handling**: Modbus exceptions such as Modbus Exception Code 03 (Invalid Data Address) or Modbus Exception Code 02 (Illegal Data Value).
  * **Modbus TCP Port**: Default port 502 for Modbus communication.

### Network Infrastructure

* **Network Type**: The communication between system components will utilize a local area network (LAN), WiFi infrastructure, or industrial Ethernet for high-speed and reliable communication.
* **Network Redundancy**: To minimize downtime, the system should include failover mechanisms and redundancy for critical components such as servers and communication devices.
* **Latency**: Network latency should be minimal, ideally below 100 ms for real-time control of shuttles and conveyor systems.

### Data Formats and Reporting Specifications

#### CSV Format

* **Purpose**: For bulk data exchange such as inventory reports, shuttle movement logs, and order status updates.
* **CSV Specification:**
  * Delimiter: Comma (,) or semicolon (;), depending on regional settings.
  * Header Row: Each CSV file starts with a header row describing the data fields.
  * Example CSV for shuttle movements:&#x20;
  * Shuttle ID, Start Location, End Location, Status, Time Stamp
  * SH001,A1,B2,Completed,2024-12-04T14:30:00
  * SH002,B2,C1,In Progress,2024-12-04T14:31:00
* **File Encoding**: UTF-8.
* **Date/Time Format**: ISO 8601 (YYYY-MM-DDTHH:mm:ss).

#### PDF Format

* **Purpose**: For generating printable reports (e.g., performance reports, maintenance logs).
* **PDF Specification:**
  * **Content Layout**: Reports are designed with a clear header, table of contents (if applicable), and footnotes.
  * **Fonts**: Standardized fonts (e.g., Arial or Times New Roman), with readable font sizes (10–12 pt for body text).
  * **Tables**: Clear and concise table formatting with borders, headers, and alternating row colors for readability.
  * **Example PDF**: A report showing daily shuttle operations:&#x20;
  * Shuttle Operations Report
  * Date: 2024-12-04

<table><thead><tr><th width="123">Shuttle ID</th><th width="144">Start Location</th><th width="137">End Location</th><th width="116"></th><th></th></tr></thead><tbody><tr><td>SH001</td><td>A1</td><td>B2</td><td>Completed</td><td>2024-12-04T14:30:00</td></tr><tr><td>SH002</td><td>B2</td><td>C1</td><td>In Progress</td><td>2024-12-04T14:31:00</td></tr></tbody></table>

#### HTML Format

* **Purpose**: For web-based reporting and dashboards for real-time monitoring of system performance.
* **HTML Specification:**
  * **Responsive Design**: The report page is responsive to work on desktop and mobile browsers.
  * **Data Representation**: Tables, charts, and dynamic elements to display real-time data.

### Integration with External Systems

#### Integration with Warehouse Management System (WMS)

* **API Endpoints:**
  * **GET /api/inventory**: Retrieve current inventory levels in the system.
  * **POST /api/order**: Submit new order requests to the system for picking.
  * **PUT /api/order/{order\_id}/status**: Update order status after completion.
* **Data Format**: JSON for API interactions with WMS.
* **Example API Request to submit an order**:&#x20;

{% hint style="info" %}
{

&#x20;    "order\_id": "ORD12345",

&#x20;    "items": \[

&#x20;        {"sku": "ITEM001", "quantity": 10},

&#x20;        {"sku": "ITEM002", "quantity": 5}

&#x20;    ],

&#x20;     "customer\_id": "CUST5678"

&#x20;}
{% endhint %}

#### Integration with ERP Systems

* The platform expose APIs for integration with the Enterprise Resource Planning (ERP) system, allowing synchronization of stock levels, order processing, and financial

\
