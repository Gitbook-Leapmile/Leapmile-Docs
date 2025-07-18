# Partner API Docs V2

### Introduction

Welcome to the Robot Manager Partner API documentation. Here, you'll find a comprehensive overview of the API endpoints available for managing tasks within the Robot Manager system. You can easily navigate to specific API documentation pages by clicking the links below.

Authorized partners will receive secure API access tokens via email.

Please note that any third parties interested in utilizing these APIs or related resources must obtain prior written permission from LeapMile Logistics Pvt. Ltd., the owner of the intellectual property, trademarks, and copyrights.

### API Interfaces

#### API Documentation and Online Test Harness

[Swagger](https://robotmanagergs.leapmile.com/robotmanager/docs#/)

#### API List:

[Create a New Tray Request](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/retrieve_tray_retrieve_tray_post)&#x20;

* To retrieve any tray, you need to pass the tray\_id, tags, which is a list, e.g., \["station", "pickup"], and order\_reference\_id which will be your ID to track the order. Order\_reference\_id is mandatory.

&#x20;      [Create list of tray requests](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/retrieve_tray_list_retrieve_tray_list_post)

*   Retrieve\_tray\_list can be used to order the list of trays at once data:&#x20;

    ```
    { 
          "details":
          [ 
                      {"tray_id": "1", "order_number": "", "order_reference_id": "", "required_tags": ["pickup", "station"]},  
                      {"tray_id": "2", "order_number": "", "order_reference_id": "", "required_tags": ["pickup", "station"]}
          ] 
    }
    ```
* **Order\_reference\_id**: This is the ID associated with the bulk order. It typically represents a high-level identifier for a group of related items or a complete purchase.
* **Order\_number**: This is the ID associated with individual items or products within the bulk order. It usually serves as a lower-level identifier for tracking specific products within the overall order.
* **NOTE:** Currently we deal with \[order\_reference\_id] so please use that and it should be unique.

[Get Status of Tray Request](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/is_tray_ready_is_tray_ready_get)&#x20;

* To check all the ready trays, call the API without the parameters.
* To check if your specific order is ready or not, then you have to pass the following parameters: tray\_id, tags (which you passed when you ordered the tray), and order\_reference\_id.

[Release Tray from Picking Station](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/release_tray_release_tray_patch)&#x20;

* To release the tray for your order, you need to pass the following parameters: tray\_id, tags, and order\_reference\_id.

[Get Picking Station Request](https://robotmanagergs.leapmile.com/robotmanager/docs#/slots/get_slot_slots_get)&#x20;

* To get the picking station, use the following parameters: slot\_status=active, tags=\["station"]

[Get Trays Request](https://robotmanagergs.leapmile.com/robotmanager/docs#/trays/get_tray_trays_get)

### Webhook API Documentation

This webhook API allows clients to register, manage, and retrieve events triggered by a robot. The API supports registering a webhook URL, sending event data (payload), and retrieving events associated with a specific robot\_id.

[Register webhook](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/callback_webhook_post)

[Get webhook](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/callback_webhook_get)

[Delete webhook](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/callback_webhook__record_id__delete)

### Steps to Use API

1. Retrieve Tray. [LINK](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/retrieve_tray_list_retrieve_tray_list_post)

* **NOTE:** Currently we deal with \[order\_reference\_id] so please use that and it should be unique. params:\
  &#x20;              tray\_id: str\
  &#x20;              required\_tags: list \[str] \
  &#x20;                      <sup>eg: \["station", "pickup"]</sup>\
  &#x20;              order\_reference\_id: str \
  &#x20;                    <sup>(a unique order id from external order for tracking the order)</sup> &#x20;
* Another way to retrieve tray:

Retrieve\_tray\_list can be used to order the list of trays at once data: [LINK](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/retrieve_tray_retrieve_tray_post)

```
{ 
      "details":
      [ 
                  {"tray_id": "1", "order_number": "", "order_reference_id": "", "required_tags": ["pickup", "station"]},  
                  {"tray_id": "2", "order_number": "", "order_reference_id": "", "required_tags": ["pickup", "station"]}
      ] 
}
```

* **Order\_reference\_id**: This is the ID associated with the bulk order. It typically represents a high-level identifier for a group of related items or a complete purchase.
* **Order\_number**: This is the ID associated with individual items or products within the bulk order. It usually serves as a lower-level identifier for tracking specific products within the overall order.
* **NOTE:** Currently we deal with \[order\_reference\_id] so please use that and it should be unique.

2. Check for retrieve tray status when your order is ready it will show up in this API call. [LINK](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/is_tray_ready_is_tray_ready_get)\
   params:\
   &#x20;               tray\_id: str \
   &#x20;               required\_tags: list \[str] \
   &#x20;                     <sup>eg: \["station", "pickup"] (pass the same tags which you passed while creating the order)</sup> \
   &#x20;               order\_reference\_id: str \
   &#x20;                   <sup>(The unique order id which you have passed while creating order)</sup>

* If the response gives you the details, that means the tray is ready to use, and the station details will be available in the response.

3. Release the tray after use. [LINK](https://robotmanagergs.leapmile.com/robotmanager/docs#/partner/release_tray_release_tray_patch)\
   params:\
   &#x20;               tray\_id: str\
   &#x20;               required\_tags: list \[str] \
   &#x20;                       <sup>eg: \["station", "pickup"] (pass the same tags which you passed while creating the order)</sup>\
   &#x20;               order\_reference\_id: str \
   &#x20;                       <sup>(The unique order id which you have passed while creating order).</sup>
