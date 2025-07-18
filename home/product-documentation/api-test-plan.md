# API Test Plan

### Introduction

This document defines the test plan for the Nanostore API. It focuses on validating the API's functionality, performance, reliability, and security. The plan ensures comprehensive coverage for robust and efficient API operations.

### Common Expected Responses

#### Success:

&#x20;    Status: 200 OK

&#x20;    Payload: Relevant details for the requested resource (e.g., user, bin, tray, product, order).

#### Error - Unauthorized:

&#x20;    Status: 401 Unauthorized

&#x20;    Payload: An error message indicating authentication is required or has failed.

#### Error - Resource Not Found:

&#x20;    Status: 404 Not Found

&#x20;    Payload: An error message indicating the resource does not exist.

#### Error - Invalid Input:

&#x20;    Status: 400 Bad Request

&#x20;    Payload: An error message indicating the reason for the invalid request.

#### Error - Server Issue:

&#x20;    Status: 500 Internal Server Error

&#x20;    Payload: Generic error message indicating server-side failure.

### Users Test Scenarios

#### Retrieve User Details:

Ensure the GET request fetches the correct user information for a valid user ID.

Endpoint: GET /nanostore/users/{user\_id} should return the user’s profile details (e.g., name, role like(drop access, pickup access, admin access).

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc4mnblbyHm77McV55ueHBH3CeJz72to_Z8OGjw1DGjSin72d4Z7mhokQ9uff7y2q7df6C1LED1ytSzibMkwEmAuRw4tFDjohLgs5_Dfts8ZquAaftGEO9bvEhMj4RDaa0wEUgBcA?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Handle Non-Existent User:

Endpoint: GET /nanostore/users/{invalid\_user\_id} should return a 404 status with an error message.\
Bad Case Output: {"status": "failure", "status\_code": 404}

### Bin Test Scenarios

#### Retrieve Bin Details

Verify that a GET request fetches details of the specified bin by its bin id.

Endpoint: GET /nanostore/bins/{bin\_id} should return bin details, including its status and products.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemj0DLM_i1PQpFZisOLMPfdVQZrp1tJ4vQvppevpGIpe0LCB8kAdQbmeR45SZGTt7rsHWRZxAMeehws3zsMSS-HseBK0G0_owTyOjNMLhh2uozaoDEFl1-vmGTwFMNAvRsPqk?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Handle Non-Existent Bins:

Endpoint: GET /nanostore/bins/{invalid\_bin\_id}\
should return a 404 status with an error message.\
Bad Case Output: {"status": "failure", "status\_code": 404}

#### Add a New Bin

Endpoint: POST /nanostore/bins/ with payload:{"robot\_id":"TEST","bin\_id":"DR1F01","bin\_height":100}

**Expect Output:** {"status": "success", "status\_code": 200}

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeylzaJx2PWpNIAeI7fOsGSPgqUt4het-tgA0nuQJDZ8RgK4BgiVI8Xwt0lT7BMuBbMilx4FCfBZ6t86ajFyKh8mqRDnyFaKzZuNsudP8pAdsBsLfydgOC2pNyM0UlPzYSz5qm-?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Error Test Scenario

Scenario 1: Robot ID Not Found in RobotManager

**Expected Output:**\
{"status": "failure", "status\_code": 404,\
"message": "Robot: \[ TEST ] details not found." }

Scenario 2: Bin Not Unique

**Expected Output:**\
{ "status": "failure", "status\_code": 404, "message": "Bin Id: \[ DR1F01 ] should be unique."}

### Tray Test Scenarios

#### Retrieve Tray Details

Verify that a GET request fetches details of the specified tray by its tray id.

Endpoint: GET /nanostore/trays/{tray\_id} should return bin details, including its status and products.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdV6QbVvugtCfQdP40e2gbbxdHBgdb575V0Y_CDvv__S7G34xnXsv9mAr_027V0tfpIq75WUS-C4_w8wO6gUCSWJNusdQvtdlSwrGuBvvapdxAOQSErhURA2QyEfRf7t1vLG0YP?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Handle Non-Existent Tray:

Endpoint: GET /nanostore/trays/

Parameters: Can include combinations such as id, status, tray\_id, or bin\_id.

Bad Case Output: {"status": "failure", "status\_code": 404}

#### Add a New Tray

Endpoint: POST /nanostore/trays/ with payload:

{"robot\_id":"R1","tray\_type":"metal\_tray","tray\_id":"TID-1000001","bin\_id":"DR1F01","tray\_height":100}

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc17kp-5BBRnOThWuDF7eNz-1AJ1K7EJ_f10MbP4fsFMPllM9vtgFkzsY-hN73tEnWyO4gsP2yVc7axJPPPJnamVCshDN7-Mn4BPcIMQf3lQuLk_vPUEDdw7q0tbcxT6Q8DDFfZuA?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

**Expect Output:** {"status": "success", "status\_code": 200}

#### Error Test Scenario

Scenario 1: Tray Not Found in RobotManager

**Expected Output:**\
{"status": "failure", "status\_code": 404,\
"message": "Robot: \[ R1 ] Tray:\[ TID-10005900 ] details not found."}

Scenario 2: Bin Already Mapped with Another Tray

**Expected Output:**\
{"status": "failure", "status\_code": 404, "message":\
"Bin Id: \[ DR1F01 ] already mapped with Tray:\[ TID-1000587 ]"}

Scenario 3: Tray and Bin Not Unique

**Expected Output:**\
{"status": "failure", "status\_code": 404, "message":\
"message": "Tray: \[ TID-1000590 ] / Bin: \[ None ] should be unique.""}

### Product Catalog Test Scenarios

Retrieve Product Catalog Details

Verify that a GET request fetches details of the specified product by its product ID.

Endpoint: GET /nanostore/product\_catalog/{product\_id} should return product details, including its status and products.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXe92q-ExQtxpnhCrpEMILtLNANpEY9uapySYvkkbIzXIZlMEvBgPukDj3ENG1tiRSxBF0HqIT3dsP9e9d3M26j8Xs8DqKATkXEosYSBSHzYBcwOw_8aW_Eaj-DfOXi_thClV26z?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Handle Non-Existent Product Catalog:

Endpoint: GET /nanostore/product\_catalog/

Parameters: Can include combinations such as id, product\_id.

Bad Case Output: {"status": "failure", "status\_code": 404}

#### Add a New Product Catalog

Endpoint: POST /nanostore/product\_catalog/ with payload:

&#x20;{ "product\_id": "00M95", "product\_description": "CRD,NTWK,DP,INTEL,25G,SFP,LP", "WSHEID":"CHBLR1","Description":"CRD,NTWK,DP,INTEL,25G,SFP,LP","PartCategory": "NON-HRM - B", "ProductGroup": "NETWORK CARD" }\


<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfBaLQtJo1TRP67WppP9DUxPOcKZixKAu5wgt3aGiMLSSzQDe5NGWwH7qV8S6daisodQAXseKwdwZ889i5tP12Z8rAhvLFr2pGQfjfMF48WMSfFZLWZTxibl1NblyuvEvwxY_DAAg?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

**Expect Output:** {"status": "success", "status\_code": 200}\
Error Test Scenario

Scenario 1: Product Not Unique

**Expected Output:**\
{ "status": "failure", "status\_code": 404,"message":\
Product ID: \[00N9G] should be unique." }

### Products Test Scenarios

**Retrieve Products Details**

Verify that a GET request fetches details of the specified product by its product ID.

Endpoint: GET /nanostore/products/{product\_id} should return product details, including its status and products.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfLzPmcj5dOp5Y6K6ml796B-QWMiSMWJ4TNu1EbG8Cj1WW-wOV7_zCCETSpBeDrDjEXeHuDBtxR0onD6K1X_9mMcMc3iKw0HWkq_ANfunseS84AtuXCjVPo0-tW76ZjNgdNMeSf?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Handle Non-Existent Product:

Endpoint: GET /nanostore/products/

Parameters: Can include combinations such as id, status or product\_id.

Bad Case Output: { "status": "failure", "status\_code": 404 }

#### Add a New Product

Endpoint: POST /nanostore/products/ with payload:

&#x20;{ "product\_id": "00M95",   "bin\_id": "DR1F01", "user\_id": "111844" }\
\
Expect Output: {"status": "success", "status\_code": 200}

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd5ZlRwaHtls6Co0cM6mEHngasekkkbjjt7F_GfrVJFemq24_C6Q3LzwsPM3KIAe9WBmKlSNQNsN41oQZU89_NnSVQ4_u26LF9jFvXlbpduvE_h0mP2S0ep94OY275Dfm51v86O9w?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Error Test Scenario

Scenario 1: Product Not Found in Product Catalog

**Expected Output:**\
{ "status": "failure", "status\_code": 404,"message":\
\[ DR1F01 ] / User: \[ 111844 ] Product: \[ TEST ] might be not valid." }\
\
Scenario 2: Bin Is Not Found in Bins

**Expected Output:**\
{ "status": "failure", "status\_code": 404,\
"message": "Bin: \[ DR1F01111 ] is not available." }

#### Orders Test Scenarios

Retrieve Order Details (Inbound/Outbound/Admin):

Verify that a GET request fetches details of the specified bin by its Order ID.

Endpoint: GET /nanostore/orders/{order\_id} should return order details, including its order status and ordered products, which we can pick or inbound.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdKsy9OUyhyV_b65K6XlGJLHLG3SwHurHVCtJ1umSdhQju0cBIDcYAbjfbctt3CcSu3ROJLAKTFfP86ZfC5VFtXWQjD9GCX3lDyB3MifXg0PaxKPTcSgkX6qaKDk5_bR0wEr_MXXg?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Create an Inbound Order

Endpoint: POST /nanostore/orders/ with payload:\
{ "user\_id": "111844",   "order\_type": "inbound", "robot\_id": "R1"  "bin\_id": "DR1F01" }

#### **Create an Outbound Order**

Endpoint: POST /nanostore/orders/ with payload:\
{ "user\_id": "111844",   "order\_type": "outbound", "robot\_id": "R1"  "bin\_id": "DR1F01" }

#### Create an Admin Order (Bin-Tray Mapping)

Endpoint: POST /nanostore/orders/ with payload:\
{ "user\_id": "111844",   "order\_type": "admin", "robot\_id": "R1"  "tray\_id": "TID-100001" }

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdwfmeH2YY_VefwIUdIsNBG27VjfmygGaqGqFcvw81VMFKMndWCJ7N9ZBSxewLqS-2gCU8gey309qlOfcgV_jdOXewvYbzmyAksh9_ni7mTArzkYKzHxuNsZkcEsE--Qf-bGigKbw?key=iyDSPDKzUmf5UwgSmxCuZtnK" alt=""><figcaption></figcaption></figure>

#### Error Test Scenario

Scenario 1: The user is not authorized to create an Order

**Expected Output:**\
{ "status": "failure", "status\_code": 404,"message":\
user: \[ 11184 ] is not valid or authorized to create order." }

Scenario 2: Bin or Tray not Found in Nanostore

**Expected Output:**\
{ "status": "failure", "status\_code": 404,\
"message":"Tray/Bin: \[None / DR1F02555] is invalid." }

Scenario 3: Robot or Tray not Found in RobotManager

**Expected Output:**\
{ "status": "failure", "status\_code": 404,\
"message":"tray is not available in the robot slot or shuttle" }
