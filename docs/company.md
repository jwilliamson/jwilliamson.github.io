# Company

The company end-point will show all of the links and properties of a company. If you have a parent/child setup, you can define the parent company ID and all the child companies will be embedded in the response. This is an admin API call so you'll need to authenticate and provide the auth-token in the header.

<pre>GET /api/v1/admin/{company_id}/company</pre>

In the example below we are only retrieving information for a child company. 

<div class="tabs">
    <ul class="tabs__menu">
        <li class="current"><a href="#tab-1">cURL</a></li>
        <li><a href="#tab-2">Sample Response Data</a></li>
    </ul>

    <div class="tab">
        <div id="tab-1" class="tab__content">
<pre>
```
  curl -X GET -H "App-Id: {app-id}" -H "App-Key: {app-key}" -H "Auth-Token: {auth-token}"
  -H "Content-Type: application/json" 
  -H "Cache-Control: no-cache"
"https://{host}.bookingbug.com/api/v1/admin/{company_id}/company"
  ```
</pre>
        </div>
        <div id="tab-2" class="tab__content">
<pre>
```
{
  "id": 50666,
  "name": "Test Child Company",
  "description": "This is a test company",
  "address_id": 52355,
  "website": "www.test.com",
  "multi_status": [
    "no_show",
    "checked_in",
    "completed"
  ],
  "numeric_widget_id": 3458242,
  "currency_code": "GBP",
  "timezone": "Europe/London",
  "country_code": "gb",
  "live": true,
  "_embedded": {
    "settings": {
      "has_coupons": true,
      "has_deals": true,
      "has_products": true,
      "has_services": true,
      "has_events": true,
      "has_classes": true,
      "payment_tax": 0,
      "currency": "GBP",
      "requires_login": false,
      "has_wallets": false,
      "_links": {
        "self": {
          "href": "https://{host}.bookingbug.com/api/v1/50666/settings"
        }
      }
    }
  },
  "_links": {
    "parent": {
      "href": "https://{host}.bookingbug.com/api/v1/company/50579"
    },
    "self": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/company"
    },
    "settings": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/settings"
    },
    "services": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/services"
    },
    "categories": {
      "href": "https://{host}.bookingbug.com/api/v1/50579/categories{/id}",
      "templated": true
    },
    "address": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/addresses/52355"
    },
    "addresses": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/addresses"
    },
    "book": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/basket/add_item{?event_id,member_id,event_chain_id,service_id,product_id,attachment_id,deal_id,package_id,bulk_purchase_id}",
      "templated": true
    },
    "space_statuses": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/space_statuses"
    },
    "named_categories": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/named_categories"
    },
    "people": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/people{?embed}",
      "templated": true
    },
    "clinics": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/clinics{/id}{?start_time,end_time,address_id,availability,start_date,end_date,resource_id,person_id}",
      "templated": true
    },
    "events": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/events{?start_date,end_date,page,per_page,resource_id,person_id,event_group_id,event_chain_id,summary,member_level_id,embed,include_non_bookable,modified_since}",
      "templated": true
    },
    "event_chains": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/event_chains{?member_level_id}"
    },
    "event_groups": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/event_groups{?page,per_page}",
      "templated": true
    },
    "client_details": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/client_details"
    },
    "packages": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/packages"
    },
    "bulk_purchases": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/bulk_purchases"
    },
    "checkout": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/basket/checkout{?member_id,take_from_wallet}"
    },
    "total": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/purchase_totals/{total_id}",
      "templated": true
    },
    "login": {
      "href": "https://{host}.bookingbug.com/api/v1/login/50666"
    },
    "client": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/client{/id}{?page,per_page,filter_by,filter_by_fields,order_by,order_by_reverse,search_by_fields}",
      "templated": true
    },
    "client_by_email": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/client/find_by_email/{email}",
      "templated": true
    },
    "booking_text": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/booking_text"
    },
    "basket": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/basket"
    },
    "days": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/day_data{?month,week,date,edate,location,service_id,event_id,person_id,resource_id,people_ids,resource_ids,person_group_id}",
      "templated": true
    },
    "times": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/time_data{?service_id,event_id,date,end_date,location,person_id,resource_id,duration,single,num_resources,group_id,resource_ids,time_zone,ignore_booking,person_group_id}",
      "templated": true
    },
    "coupon": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/basket/coupon"
    },
    "email_password_reset": {
      "href": "https://{host}.bookingbug.com/api/v1/login/50666/email_password_reset"
    },
    "member_levels": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/membership_levels"
    },
    "facebook_login": {
      "href": "https://{host}.bookingbug.com/api/v1/login/50666/facebook"
    },
    "new_person": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/people/new{?signup}",
      "templated": true
    },
    "schedules": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/schedules{?start_date,end_date,page,per_page}",
      "templated": true
    },
    "new_schedule": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/schedules/new",
      "templated": true
    },
    "administrators": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/administrators"
    },
    "new_administrator": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/administrators/new",
      "templated": true
    },
    "slots": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/slots{?start_date,end_date,date,resource_id,service_id,person_id,page,per_page}",
      "templated": true
    },
    "new_event_chain": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/event_chains/new",
      "templated": true
    },
    "new_event_group": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/event_groups/new",
      "templated": true
    },
    "new_address": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/addresses/new",
      "templated": true
    },
    "calendar_events": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/calendar_events{/id}{?start_time,end_time,address_id,availability,start_date,end_date,resource_id}",
      "templated": true
    },
    "new_service": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/services/new",
      "templated": true
    },
    "bookings": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/bookings{/id}{?start_date,end_date,page,per_page,include_cancelled,modified_since,slot_id,event_id,resource_id,service_id,person_id,client_id,filter_by_fields,order_by,order_by_reverse,start_time,end_time,locale,clinic_id}",
      "templated": true
    },
    "queuers": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/queuers{?client_queue_ids}",
      "templated": true
    },
    "client_queues": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/client_queues"
    },
    "new_queuer": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/queuers/new",
      "templated": true
    },
    "pusher": {
      "href": "https://{host}.bookingbug.com/api/v1/push/50666/pusher.json"
    },
    "external_bookings": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/external_bookings{?start,end}",
      "templated": true
    },
    "audit_details_search": {
      "href": "https://{host}.bookingbug.com/api/v1/admin/50666/auditlog/details_search"
    }
  }
}
  ```
</pre>
        </div>
        </div>
        </div>


## Settings

You can retrieve settings block for a company. This is useful for checking if the company has services, events etc configured. 

<pre>GET /api/v1/{company_id}/settings</pre>

<div class="tabs">
    <ul class="tabs__menu">
        <li class="current"><a href="#tab-1">cURL</a></li>
        <li><a href="#tab-2">Sample Response Data</a></li>
    </ul>

    <div class="tab">
        <div id="tab-1" class="tab__content">
<pre>
```
  curl -X GET -H "App-Id: {app-id}" -H "App-Key: {app-key}"
  -H "Content-Type: application/json" 
  -H "Cache-Control: no-cache"
"https://{host}.bookingbug.com/api/v1/{company_id}/settings"
  ```
</pre>
        </div>
        <div id="tab-2" class="tab__content">
<pre>
```
{
  "has_coupons": true,
  "has_deals": true,
  "has_products": true,
  "has_services": true,
  "has_events": true,
  "has_classes": true,
  "payment_tax": 0,
  "currency": "GBP",
  "requires_login": false,
  "has_wallets": false,
  "_links": {
    "self": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/settings"
    }
  }
}
  ```
</pre>
        </div>
        </div>
        </div>
    

## Addresses

Get all addresses for a company. A company can be configured to have many addresses. 

<pre>GET /api/vi/{company_id}/addresses</pre>

Read one address
<pre>GET /api/vi/{company_id}/addresses/{address_id}</pre>

<div class="tabs">
    <ul class="tabs__menu">
        <li class="current"><a href="#tab-1">cURL</a></li>
        <li><a href="#tab-2">Sample Response Data</a></li>
    </ul>

    <div class="tab">
        <div id="tab-1" class="tab__content">
<pre>
```
  curl -X GET -H "App-Id: {app-id}" -H "App-Key: {app-key}" -H "Auth-Token: {auth-token}"
  -H "Content-Type: application/json" 
  -H "Cache-Control: no-cache"
"https://{host}.bookingbug.com/api/v1/{company_id}/addresses"
  ```
</pre>
        </div>
        <div id="tab-2" class="tab__content">
<pre>
```
{
  "total_entries": 2,
  "_embedded": {
    "addresses": [
      {
        "id": 52355,
        "name": "London Office",
        "address1": "111 London Road",
        "address2": "",
        "address3": "",
        "address4": "London",
        "address5": "",
        "postcode": "E11 11",
        "country": "United Kingdom",
        "lat": 51.5697709,
        "long": 0.0100555,
        "map_url": "",
        "map_marker": "111+london+Road,+London,+E11+11,+United+Kingdom",
        "phone": "",
        "homephone": "",
        "extra": {},
        "_links": {
          "self": {
            "href": "https://{host}.bookingbug.com/api/v1/admin/50666/addresses/52355"
          },
          "edit": {
            "href": "https://{host}.bookingbug.com/api/v1/admin/50666/addresses/52355/edit"
          }
        }
      },
      {
        "id": 57120,
        "name": "East Office",
        "address1": "23 East",
        "address2": "2nd floor",
        "address4": "London",
        "postcode": "SW1 8UY",
        "country": "United Kingdom",
        "lat": 50.8616024,
        "long": -3.380951,
        "map_marker": "23+East,+2nd+floor,+London,+SW1+8UY,+United+Kingdom",
        "phone": "",
        "extra": {
          "branch_id": "2"
        },
        "_links": {
          "self": {
            "href": "https://{host}.bookingbug.com/api/v1/50666/addresses/57120"
          },
          "edit": {
            "href": "https://{host}.bookingbug.com/api/v1/50666/addresses/57120/edit"
          }
        }
      }
    ]
  },
  "_links": {
    "self": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/addresses"
    },
    "new": {
      "href": "https://{host}.bookingbug.com/api/v1/50666/addresses/new",
      "templated": true
    }
  }
}
  ```
</pre>
        </div>
        </div>
        </div>
