---
title: Banking API v0.0.1
language_tabs:
  - ruby: Ruby
  - python: Python
language_clients:
  - ruby: ""
  - python: ""
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="banking-api">Banking API v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Flow Finance Banking API

Base URLs:

* <a href="/">/</a>

<h1 id="banking-api-auth">Auth</h1>

## Obtain an access token

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json'
}

result = RestClient.post '/api/v1/oauth2/token',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('/api/v1/oauth2/token', headers = headers)

print(r.json())

```

`POST /api/v1/oauth2/token`

The `client_credentials` grant type is used by clients to obtain an access token outside of the context of a user.

> Body parameter

```json
{
  "grant_type": "client_credentials",
  "client_id": "string",
  "client_secret": "string"
}
```

<h3 id="obtain-an-access-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Credentials](#schemacredentials)|true|none|

<h3 id="obtain-an-access-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="banking-api-persons">Persons</h1>

## Retrieve all persons

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/persons',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/persons', headers = headers)

print(r.json())

```

`GET /api/v1/persons`

Retrieve all persons created under your partner_id.

<h3 id="retrieve-all-persons-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|

<h3 id="retrieve-all-persons-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for a person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/persons',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/persons', headers = headers)

print(r.json())

```

`POST /api/v1/persons`

Create the resource for a person. In the context of a business, a person may be its legal representative or its beneficial owner.

> Body parameter

```json
{
  "phone_number": "string",
  "taxpayer_id": "string",
  "occupation": "string",
  "nationality": "string",
  "pep": true,
  "birth_date": "string",
  "marital_status": "string",
  "full_name": "string",
  "email_address": "string",
  "mothers_name": "string",
  "drivers_license_number": "string",
  "marital_property_system": "string"
}
```

<h3 id="create-the-resource-for-a-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|body|body|[PersonCreate](#schemapersoncreate)|true|none|

<h3 id="create-the-resource-for-a-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.get '/api/v1/persons/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.get('/api/v1/persons/{id}', headers = headers)

print(r.json())

```

`GET /api/v1/persons/{id}`

Retrieve the given person.

<h3 id="retrieve-the-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-the-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Update the details of a person resource

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.patch '/api/v1/persons/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.patch('/api/v1/persons/{id}', headers = headers)

print(r.json())

```

`PATCH /api/v1/persons/{id}`

Update the details of a person resource.

> Body parameter

```json
{
  "phone_number": "string",
  "taxpayer_id": "string",
  "occupation": "string",
  "nationality": "string",
  "pep": true,
  "birth_date": "string",
  "marital_status": "string",
  "full_name": "string",
  "email_address": "string",
  "mothers_name": "string",
  "drivers_license_number": "string",
  "marital_property_system": "string"
}
```

<h3 id="update-the-details-of-a-person-resource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[PersonUpdate](#schemapersonupdate)|true|none|

<h3 id="update-the-details-of-a-person-resource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete the given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/persons/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/persons/{id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/persons/{id}`

Delete the given person.

<h3 id="delete-the-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|

<h3 id="delete-the-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all documents related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/persons/{id}/documents',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/persons/{id}/documents', headers = headers)

print(r.json())

```

`GET /api/v1/persons/{id}/documents`

Retrieve all documents related to a given person.

<h3 id="retrieve-all-documents-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-documents-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) person documents

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/persons/{id}/documents',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/persons/{id}/documents', headers = headers)

print(r.json())

```

`POST /api/v1/persons/{id}/documents`

Create the resource for one (or multiple) person documents.

> Body parameter

```json
[
  {
    "document-type": "string",
    "document-value": "string"
  }
]
```

<h3 id="create-the-resource-for-one-(or-multiple)-person-documents-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[DocumentsCreate](#schemadocumentscreate)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-person-documents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Obtain an access token

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/persons/{id}/documents/{document-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/persons/{id}/documents/{document-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/persons/{id}/documents/{document-id}`

The `client_credentials` grant type is used by clients to obtain an access token outside of the context of a user.

<h3 id="obtain-an-access-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|document-id|path|string(uuid)|true|none|

<h3 id="obtain-an-access-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all addresses related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/persons/{id}/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/persons/{id}/addresses', headers = headers)

print(r.json())

```

`GET /api/v1/persons/{id}/addresses`

Retrieve all addresses related to a given person.

<h3 id="retrieve-all-addresses-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-addresses-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) address related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/persons/{id}/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/persons/{id}/addresses', headers = headers)

print(r.json())

```

`POST /api/v1/persons/{id}/addresses`

Create the resource for one (or multiple) address related to a given person.

> Body parameter

```json
{
  "street_name": "string",
  "street_number": "string",
  "postal_code": "string",
  "district": "string",
  "city": "string",
  "state_code": "string",
  "country": "string",
  "extra_address_info": "string"
}
```

<h3 id="create-the-resource-for-one-(or-multiple)-address-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[Address](#schemaaddress)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-address-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete an address related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/persons/{id}/addresses/{address-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/persons/{id}/addresses/{address-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/persons/{id}/addresses/{address-id}`

Delete an address related to a given person.

<h3 id="delete-an-address-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|address-id|path|integer(int64)|true|none|

<h3 id="delete-an-address-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all external accounts related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/persons/{id}/external-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/persons/{id}/external-accounts', headers = headers)

print(r.json())

```

`GET /api/v1/persons/{id}/external-accounts`

Retrieve all external accounts related to a given person.

<h3 id="retrieve-all-external-accounts-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-external-accounts-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) external account related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/persons/{id}/external-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/persons/{id}/external-accounts', headers = headers)

print(r.json())

```

`POST /api/v1/persons/{id}/external-accounts`

Create the resource for one (or multiple) external account related to a given person.

> Body parameter

```json
{
  "is_default": true,
  "bank_code": "string",
  "bank_account": "string",
  "bank_branch": "string",
  "account_holder_name": "string",
  "account_holder_type": "string",
  "account_holder_id": "string"
}
```

<h3 id="create-the-resource-for-one-(or-multiple)-external-account-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[ExternalAccountWrite](#schemaexternalaccountwrite)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-external-account-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete an external account related to a given person

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/persons/{id}/external-accounts/{external-account-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/persons/{id}/external-accounts/{external-account-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/persons/{id}/external-accounts/{external-account-id}`

Delete an external account related to a given person.

<h3 id="delete-an-external-account-related-to-a-given-person-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|external-account-id|path|string(uuid)|true|none|

<h3 id="delete-an-external-account-related-to-a-given-person-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="banking-api-businesses">Businesses</h1>

## Retrieve all businesses

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/businesses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/businesses', headers = headers)

print(r.json())

```

`GET /api/v1/businesses`

Retrieve all businesses created under your partner_id.

<h3 id="retrieve-all-businesses-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|

<h3 id="retrieve-all-businesses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for a business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/businesses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/businesses', headers = headers)

print(r.json())

```

`POST /api/v1/businesses`

Create the resource for a business. A business is the representation of a juridical person (a legal person) in our system. This representation is necessarily made up of at least one natural person attached to it.

> Body parameter

```json
{
  "legal_name": "string",
  "phone_number": "string",
  "taxpayer_id": "string",
  "incorporation_type": "string",
  "industry_classification": "string",
  "name": "string",
  "email_address": "string"
}
```

<h3 id="create-the-resource-for-a-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|body|body|[BusinessCreate](#schemabusinesscreate)|true|none|

<h3 id="create-the-resource-for-a-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.get '/api/v1/businesses/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.get('/api/v1/businesses/{id}', headers = headers)

print(r.json())

```

`GET /api/v1/businesses/{id}`

Retrieve the given business.

<h3 id="retrieve-the-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-the-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Update the details of a business resource

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.patch '/api/v1/businesses/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.patch('/api/v1/businesses/{id}', headers = headers)

print(r.json())

```

`PATCH /api/v1/businesses/{id}`

Update the details of a business resource.

> Body parameter

```json
{
  "legal_name": "string",
  "phone_number": "string",
  "taxpayer_id": "string",
  "incorporation_type": "string",
  "industry_classification": "string",
  "name": "string",
  "email_address": "string"
}
```

<h3 id="update-the-details-of-a-business-resource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[BusinessUpdate](#schemabusinessupdate)|true|none|

<h3 id="update-the-details-of-a-business-resource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete the given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/businesses/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/businesses/{id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/businesses/{id}`

Delete the given business.

<h3 id="delete-the-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|

<h3 id="delete-the-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Link a given business to a person or to another business 

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/businesses/{id}/relations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/businesses/{id}/relations', headers = headers)

print(r.json())

```

`POST /api/v1/businesses/{id}/relations`

Link a given business to a person or to another business.

> Body parameter

```json
{
  "person_id": 0
}
```

<h3 id="link-a-given-business-to-a-person-or-to-another-business--parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[Relation](#schemarelation)|true|none|

<h3 id="link-a-given-business-to-a-person-or-to-another-business--responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all relations to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/businesses/{id}/relations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/businesses/{id}/relations', headers = headers)

print(r.json())

```

`GET /api/v1/businesses/{id}/relations`

Retrieve all relations to a given business.

<h3 id="retrieve-all-relations-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-relations-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Obtain an access token

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/businesses/{id}/documents/{document-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/businesses/{id}/documents/{document-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/businesses/{id}/documents/{document-id}`

The `client_credentials` grant type is used by clients to obtain an access token outside of the context of a user.

<h3 id="obtain-an-access-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|document-id|path|string(uuid)|true|none|

<h3 id="obtain-an-access-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all documents related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/businesses/{id}/documents',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/businesses/{id}/documents', headers = headers)

print(r.json())

```

`GET /api/v1/businesses/{id}/documents`

Retrieve all documents related to a given business.

<h3 id="retrieve-all-documents-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-documents-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) document related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/businesses/{id}/documents',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/businesses/{id}/documents', headers = headers)

print(r.json())

```

`POST /api/v1/businesses/{id}/documents`

Create the resource for one (or multiple) document related to a given business.

> Body parameter

```json
[
  {
    "document-type": "string",
    "document-value": "string"
  }
]
```

<h3 id="create-the-resource-for-one-(or-multiple)-document-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[DocumentsCreate](#schemadocumentscreate)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-document-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all addresses related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/businesses/{id}/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/businesses/{id}/addresses', headers = headers)

print(r.json())

```

`GET /api/v1/businesses/{id}/addresses`

Retrieve all addresses related to a given business.

<h3 id="retrieve-all-addresses-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-addresses-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) addresses related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/businesses/{id}/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/businesses/{id}/addresses', headers = headers)

print(r.json())

```

`POST /api/v1/businesses/{id}/addresses`

Create the resource for one (or multiple) addresses related to a given business.

> Body parameter

```json
{
  "street_name": "string",
  "street_number": "string",
  "postal_code": "string",
  "district": "string",
  "city": "string",
  "state_code": "string",
  "country": "string",
  "extra_address_info": "string"
}
```

<h3 id="create-the-resource-for-one-(or-multiple)-addresses-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[Address](#schemaaddress)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-addresses-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete an address related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/businesses/{id}/addresses/{address-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/businesses/{id}/addresses/{address-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/businesses/{id}/addresses/{address-id}`

Delete an address related to a given business.

<h3 id="delete-an-address-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|address-id|path|integer(int64)|true|none|

<h3 id="delete-an-address-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all external accounts related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/businesses/{id}/external-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/businesses/{id}/external-accounts', headers = headers)

print(r.json())

```

`GET /api/v1/businesses/{id}/external-accounts`

Retrieve all external accounts related to a given business.

<h3 id="retrieve-all-external-accounts-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|integer(int64)|true|none|

<h3 id="retrieve-all-external-accounts-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for one (or multiple) external account related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/businesses/{id}/external-accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/businesses/{id}/external-accounts', headers = headers)

print(r.json())

```

`POST /api/v1/businesses/{id}/external-accounts`

Create the resource for one (or multiple) external account related to a given business.

> Body parameter

```json
{
  "is_default": true,
  "bank_code": "string",
  "bank_account": "string",
  "bank_branch": "string",
  "account_holder_name": "string",
  "account_holder_type": "string",
  "account_holder_id": "string"
}
```

<h3 id="create-the-resource-for-one-(or-multiple)-external-account-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|body|body|[ExternalAccountWrite](#schemaexternalaccountwrite)|true|none|

<h3 id="create-the-resource-for-one-(or-multiple)-external-account-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Delete an external account related to a given business

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.delete '/api/v1/businesses/{id}/external-accounts/{external-account-id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.delete('/api/v1/businesses/{id}/external-accounts/{external-account-id}', headers = headers)

print(r.json())

```

`DELETE /api/v1/businesses/{id}/external-accounts/{external-account-id}`

Delete an external account related to a given business.

<h3 id="delete-an-external-account-related-to-a-given-business-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|integer(int64)|true|none|
|external-account-id|path|string(uuid)|true|none|

<h3 id="delete-an-external-account-related-to-a-given-business-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="banking-api-loan-preview">Loan Preview</h1>

## Preview the details of a loan

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/loan-preview',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/loan-preview', headers = headers)

print(r.json())

```

`POST /api/v1/loan-preview`

Preview the details of a loan.

> Body parameter

```json
{
  "requested_amount": 0,
  "interest_rate": 0,
  "tac_amount": 0,
  "finance_fee": 0,
  "iof_rate_base": 0,
  "iof_rate_daily": 0,
  "num_periods": 0,
  "creation_date": "2019-08-24"
}
```

<h3 id="preview-the-details-of-a-loan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|body|body|[LoanPreview](#schemaloanpreview)|true|none|

<h3 id="preview-the-details-of-a-loan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="banking-api-loans">Loans</h1>

## Retrieve all loans

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/loans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/loans', headers = headers)

print(r.json())

```

`GET /api/v1/loans`

Retrieve all loans created under your partner_id.

<h3 id="retrieve-all-loans-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|

<h3 id="retrieve-all-loans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the resource for a loan

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/loans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/loans', headers = headers)

print(r.json())

```

`POST /api/v1/loans`

Create the resource for a loan.

> Body parameter

```json
{
  "schedule": "monthly",
  "issue_date": "2019-08-24",
  "num_payments": 0,
  "iof_rate_base": 0,
  "finance_fee": 0,
  "requested_amount": 0,
  "interest_rate": 0,
  "tac_amount": 0,
  "disbursement_date": "2019-08-24",
  "loan_type": "pj",
  "first_payment": "2019-08-24",
  "iof_rate_daily": 0
}
```

<h3 id="create-the-resource-for-a-loan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|body|body|[LoanWrite](#schemaloanwrite)|true|none|

<h3 id="create-the-resource-for-a-loan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the given loan

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string'
}

result = RestClient.get '/api/v1/loans/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string'
}

r = requests.get('/api/v1/loans/{id}', headers = headers)

print(r.json())

```

`GET /api/v1/loans/{id}`

Retrieve the given loan.

<h3 id="retrieve-the-given-loan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|string(uuid)|true|none|

<h3 id="retrieve-the-given-loan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all signatures related to a given loan

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'auth-token' => 'string',
  'range' => 'string'
}

result = RestClient.get '/api/v1/loans/{id}/signatures',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'auth-token': 'string',
  'range': 'string'
}

r = requests.get('/api/v1/loans/{id}/signatures', headers = headers)

print(r.json())

```

`GET /api/v1/loans/{id}/signatures`

Retrieve all signatures related to a given loan.

<h3 id="retrieve-all-signatures-related-to-a-given-loan-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|range|header|string|false|none|
|id|path|string(uuid)|true|none|

<h3 id="retrieve-all-signatures-related-to-a-given-loan-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

## Create the the details of a signature

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'auth-token' => 'string'
}

result = RestClient.post '/api/v1/loans/{id}/signatures',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'auth-token': 'string'
}

r = requests.post('/api/v1/loans/{id}/signatures', headers = headers)

print(r.json())

```

`POST /api/v1/loans/{id}/signatures`

Create the the details of a signature.

> Body parameter

```json
{
  "signed_at": "2019-08-24T14:15:22Z",
  "ip_address": "string",
  "user_agent": "string",
  "person_id": 0
}
```

<h3 id="create-the-the-details-of-a-signature-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|auth-token|header|string|true|none|
|id|path|string(uuid)|true|none|
|body|body|[Signature](#schemasignature)|true|none|

<h3 id="create-the-the-details-of-a-signature-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|none|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Address">Address</h2>
<!-- backwards compatibility -->
<a id="schemaaddress"></a>
<a id="schema_Address"></a>
<a id="tocSaddress"></a>
<a id="tocsaddress"></a>

```json
{
  "street_name": "string",
  "street_number": "string",
  "postal_code": "string",
  "district": "string",
  "city": "string",
  "state_code": "string",
  "country": "string",
  "extra_address_info": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|street_name|string|true|none|none|
|street_number|string|true|none|none|
|postal_code|string|true|none|none|
|district|string|true|none|none|
|city|string|true|none|none|
|state_code|string|true|none|none|
|country|string|true|none|none|
|extra_address_info|string|false|none|none|

<h2 id="tocS_BusinessCreate">BusinessCreate</h2>
<!-- backwards compatibility -->
<a id="schemabusinesscreate"></a>
<a id="schema_BusinessCreate"></a>
<a id="tocSbusinesscreate"></a>
<a id="tocsbusinesscreate"></a>

```json
{
  "legal_name": "string",
  "phone_number": "string",
  "taxpayer_id": "string",
  "incorporation_type": "string",
  "industry_classification": "string",
  "name": "string",
  "email_address": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|legal_name|string|true|none|none|
|phone_number|string|true|none|none|
|taxpayer_id|string|true|none|none|
|incorporation_type|string|true|none|none|
|industry_classification|string|true|none|none|
|name|string|false|none|none|
|email_address|string|false|none|none|

<h2 id="tocS_BusinessUpdate">BusinessUpdate</h2>
<!-- backwards compatibility -->
<a id="schemabusinessupdate"></a>
<a id="schema_BusinessUpdate"></a>
<a id="tocSbusinessupdate"></a>
<a id="tocsbusinessupdate"></a>

```json
{
  "legal_name": "string",
  "phone_number": "string",
  "taxpayer_id": "string",
  "incorporation_type": "string",
  "industry_classification": "string",
  "name": "string",
  "email_address": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|legal_name|string|false|none|none|
|phone_number|string|false|none|none|
|taxpayer_id|string|false|none|none|
|incorporation_type|string|false|none|none|
|industry_classification|string|false|none|none|
|name|string|false|none|none|
|email_address|string|false|none|none|

<h2 id="tocS_Credentials">Credentials</h2>
<!-- backwards compatibility -->
<a id="schemacredentials"></a>
<a id="schema_Credentials"></a>
<a id="tocScredentials"></a>
<a id="tocscredentials"></a>

```json
{
  "grant_type": "client_credentials",
  "client_id": "string",
  "client_secret": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|grant_type|string|true|none|none|
|client_id|string|true|none|none|
|client_secret|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|grant_type|client_credentials|

<h2 id="tocS_DocumentsCreate">DocumentsCreate</h2>
<!-- backwards compatibility -->
<a id="schemadocumentscreate"></a>
<a id="schema_DocumentsCreate"></a>
<a id="tocSdocumentscreate"></a>
<a id="tocsdocumentscreate"></a>

```json
{
  "document-type": "string",
  "document-value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|document-type|string|true|none|none|
|document-value|string|true|none|none|

<h2 id="tocS_ExternalAccountWrite">ExternalAccountWrite</h2>
<!-- backwards compatibility -->
<a id="schemaexternalaccountwrite"></a>
<a id="schema_ExternalAccountWrite"></a>
<a id="tocSexternalaccountwrite"></a>
<a id="tocsexternalaccountwrite"></a>

```json
{
  "is_default": true,
  "bank_code": "string",
  "bank_account": "string",
  "bank_branch": "string",
  "account_holder_name": "string",
  "account_holder_type": "string",
  "account_holder_id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_default|boolean|true|none|none|
|bank_code|string|true|none|none|
|bank_account|string|true|none|none|
|bank_branch|string|true|none|none|
|account_holder_name|string|true|none|none|
|account_holder_type|string|true|none|none|
|account_holder_id|string|true|none|none|

<h2 id="tocS_LoanPreview">LoanPreview</h2>
<!-- backwards compatibility -->
<a id="schemaloanpreview"></a>
<a id="schema_LoanPreview"></a>
<a id="tocSloanpreview"></a>
<a id="tocsloanpreview"></a>

```json
{
  "requested_amount": 0,
  "interest_rate": 0,
  "tac_amount": 0,
  "finance_fee": 0,
  "iof_rate_base": 0,
  "iof_rate_daily": 0,
  "num_periods": 0,
  "creation_date": "2019-08-24"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|requested_amount|number(double)|true|none|none|
|interest_rate|number(double)|true|none|none|
|tac_amount|number(double)|true|none|none|
|finance_fee|number(double)|true|none|none|
|iof_rate_base|number(double)|true|none|none|
|iof_rate_daily|number(double)|true|none|none|
|num_periods|integer(int64)|true|none|none|
|creation_date|string(date)|true|none|none|

<h2 id="tocS_LoanWrite">LoanWrite</h2>
<!-- backwards compatibility -->
<a id="schemaloanwrite"></a>
<a id="schema_LoanWrite"></a>
<a id="tocSloanwrite"></a>
<a id="tocsloanwrite"></a>

```json
{
  "schedule": "monthly",
  "issue_date": "2019-08-24",
  "num_payments": 0,
  "iof_rate_base": 0,
  "finance_fee": 0,
  "requested_amount": 0,
  "interest_rate": 0,
  "tac_amount": 0,
  "disbursement_date": "2019-08-24",
  "loan_type": "pj",
  "first_payment": "2019-08-24",
  "iof_rate_daily": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schedule|string|true|none|none|
|issue_date|string(date)|true|none|none|
|num_payments|integer(int64)|true|none|none|
|iof_rate_base|number(double)|true|none|none|
|finance_fee|integer(int64)|true|none|none|
|requested_amount|integer(int64)|true|none|none|
|interest_rate|number(double)|true|none|none|
|tac_amount|integer(int64)|true|none|none|
|disbursement_date|string(date)|true|none|none|
|loan_type|string|true|none|none|
|first_payment|string(date)|true|none|none|
|iof_rate_daily|number(double)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|schedule|monthly|
|loan_type|pj|
|loan_type|pf|

<h2 id="tocS_PersonCreate">PersonCreate</h2>
<!-- backwards compatibility -->
<a id="schemapersoncreate"></a>
<a id="schema_PersonCreate"></a>
<a id="tocSpersoncreate"></a>
<a id="tocspersoncreate"></a>

```json
{
  "phone_number": "string",
  "taxpayer_id": "string",
  "occupation": "string",
  "nationality": "string",
  "pep": true,
  "birth_date": "string",
  "marital_status": "string",
  "full_name": "string",
  "email_address": "string",
  "mothers_name": "string",
  "drivers_license_number": "string",
  "marital_property_system": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone_number|string|true|none|none|
|taxpayer_id|string|true|none|none|
|occupation|string|true|none|none|
|nationality|string|true|none|none|
|pep|boolean|true|none|none|
|birth_date|string|true|none|none|
|marital_status|string|false|none|none|
|full_name|string|true|none|none|
|email_address|string|false|none|none|
|mothers_name|string|false|none|none|
|drivers_license_number|string|false|none|none|
|marital_property_system|string|false|none|none|

<h2 id="tocS_PersonUpdate">PersonUpdate</h2>
<!-- backwards compatibility -->
<a id="schemapersonupdate"></a>
<a id="schema_PersonUpdate"></a>
<a id="tocSpersonupdate"></a>
<a id="tocspersonupdate"></a>

```json
{
  "phone_number": "string",
  "taxpayer_id": "string",
  "occupation": "string",
  "nationality": "string",
  "pep": true,
  "birth_date": "string",
  "marital_status": "string",
  "full_name": "string",
  "email_address": "string",
  "mothers_name": "string",
  "drivers_license_number": "string",
  "marital_property_system": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone_number|string|false|none|none|
|taxpayer_id|string|false|none|none|
|occupation|string|false|none|none|
|nationality|string|false|none|none|
|pep|boolean|false|none|none|
|birth_date|string|false|none|none|
|marital_status|string|false|none|none|
|full_name|string|false|none|none|
|email_address|string|false|none|none|
|mothers_name|string|false|none|none|
|drivers_license_number|string|false|none|none|
|marital_property_system|string|false|none|none|

<h2 id="tocS_Relation">Relation</h2>
<!-- backwards compatibility -->
<a id="schemarelation"></a>
<a id="schema_Relation"></a>
<a id="tocSrelation"></a>
<a id="tocsrelation"></a>

```json
{
  "person_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|person_id|integer(int64)|true|none|none|

<h2 id="tocS_Signature">Signature</h2>
<!-- backwards compatibility -->
<a id="schemasignature"></a>
<a id="schema_Signature"></a>
<a id="tocSsignature"></a>
<a id="tocssignature"></a>

```json
{
  "signed_at": "2019-08-24T14:15:22Z",
  "ip_address": "string",
  "user_agent": "string",
  "person_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|signed_at|string(date-time)|true|none|none|
|ip_address|string|true|none|none|
|user_agent|string|true|none|none|
|person_id|integer(int64)|true|none|none|

