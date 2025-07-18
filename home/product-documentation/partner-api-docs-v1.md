# Partner API Docs V1

### Introduction

Welcome to the Robot Manager Partner API documentation. Here, you'll find a comprehensive overview of the API endpoints available for managing tasks within the Robot Manager system. You can easily navigate to specific API documentation pages by clicking the links below.

Authorized partners will receive secure API access tokens via email.

Please note that any third parties interested in utilizing these APIs or related resources must obtain prior written permission from LeapMile Logistics Pvt. Ltd., the owner of the intellectual property, trademarks, and copyrights.

### Installation Steps

### STEP 1: Developer Environment Requirements

Ensure the developer environment has Python 3.11 running on Ubuntu Linux or a similar compatible environment.

### STEP 2: Download PartnerAPI Package

[Download Package](https://leapmile-website.blr1.digitaloceanspaces.com/apidocs/partnerapi.zip)\
Download and unzip this file into a subfolder of your choice. Move into the partnerapi folder.\


### STEP 3: Install Required Python Packages

Install required python packages by running the following command (MacOS and Windows may have different commands):

```
pip3 install -r requirements.txt
```

### STEP 4: Update Configuration File with Assigned Token

Edit the file rmutils\_configuration.py and update ROBOT\_API\_TOKEN with the token assigned via email.

### STEP 5: Run API Example Script

There are multiple examples included to assist the user in understanding different aspects of the API. In the partner folder, run the command:

```
python3 apisample.py
```

### API Interfaces

#### API Documentation and Online Test Harness

&#x20;     [Swagger](https://robotmanagerv1staging.qikpod.com:8981/docs)

#### API List:

&#x20;     [Create a New Tray Request](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/task_robotmanager_task__post)\
&#x20;     [Get Status of Tray Request](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/task_robotmanager_task__get)\
&#x20;     [Release Tray from Picking Station](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/task_robotmanager_task_pickup_completed__task_id__patch)\
&#x20;     [Cancel Submitted Request](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/task_robotmanager_task_cancel_task__patch)

### Test Warehouse Configaration

#### Test Nanowarehouse Setup:

#### &#x20;   Tray IDs

&#x20;     T1, T2, T3, T4

#### &#x20;   Picking Station IDs

&#x20;     PS-1 - friendly name positioned at Row 0, Rack 1, Slot 0, Depth 1, Tags: A \
&#x20;     PS-2 - friendly name positioned at Row 0, Rack 2, Slot 0, Depth 1, Tags: A \
&#x20;     PS-3 - friendly name positioned at Row 0, Rack 3, Slot 0, Depth 1, Tags: B \
&#x20;     PS-4 - friendly name positioned at Row 0, Rack 4, Slot 0, Depth 1, Tags: B

#### Nanowarehouse Dashboard:

&#x20;   [Click Here to Access Dashboard](https://dashboard-gsgv2.flutterflow.app/)\
&#x20;    Within the dashboard, follow the steps below:

* Select the robotmanagerv1staging (for Staging)
* Enter the phone number: 9999999999 and OTP: 999999
* Select the robot name from the dropdown: GS-S1

### Demo Scripts:

apisample.py - python script that provides a clear sample usage for all the above APIs.

### Webhook API Documentation

This Webhook API allows clients to register, manage, and retrieve events triggered by a robot. The API supports registering a webhook URL, sending event data (payload), and retrieving events associated with a specific robot\_id.\
&#x20;     [Register webhook url](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/callback_robotmanager_webhook__post)\
&#x20;     [Get webhook url details](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/callback_robotmanager_webhook__get)\
&#x20;     [Delete webhook url](https://robotmanagerv1staging.qikpod.com:8981/docs#/PARTNER/callback_robotmanager_webhook__record_id__delete)\


### Example of Setting up a Webhook URL with FastAPI:

```
from fastapi import FastAPI, Request, Response, Body
import uvicorn

app = FastAPI()

@app.post("/api/")
async def users(request: Request,fastapi_response: Response,record_dict: dict = Body(...)):
	"""After registering this URL. it will start getting called by the robotmanager when the task tray is ready to use"""
	print(record_dict)
    return record_dict


if __name__ == "__main__":
    # Run the application using Uvicorn
    uvicorn.run(app, host="use the cloud host", port=8000, reload=True)
            
```

### Robot Instalization (Advanced)

⚠️ Warning: All data will be deleted and/or reset if you invoke this command!!!

Please note that running the robot initialization script (`rmutils_import.py`) will clear all previous data from the database. Ensure you have made the necessary backups before running this script. Once this initialization script is executed, all existing robot data will be reset to its initial state. Proceed with caution!

This project provides a Python-based system to import, initialize, and configure robots. The core of this setup is based on the `rmutils_import.py` file, which handles the first-time initialization of the robot’s data and settings.

#### Initialization Steps:

Open a terminal or command prompt. Navigate to the following directory: partnerapi Run the following command to start the initialization process:

```
python3 rmutils_import.py
```
