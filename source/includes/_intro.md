# Welcome to Flow Finance Docs


Welcome to the API documentation of Flow Finance. We help companies build and launch industry leading financial products on top of our banking infrastructure. This API reference provides information on available endpoints and how to interact with them. All of our endpoints are guided by REST, have predictable, resource-oriented URLs, and use HTTP response codes to indicate errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs, which are understood by off-the-shelf HTTP clients. JSON is returned by all API responses, including errors.


# Getting Started

Follow the steps below to get started:

  * Contact our sales team to register your platform and obtain your auth credentials.
  * You will be assigned an Integration Engineer who will guide you through the integration process.
  * Issue test requests using our sandbox environment.


# Authentication
Every request must be signed with an API key. For this, obtain an API Key from your Customer Support, as described in How to get the API key. Then set this key to the `auth-token` header value.


# Versioning
Our API supports versioning of its endpoints through a version suffix in the endpoint URL. This suffix has the following format: "vXX", where XX is the version number.

> For example:

```shell
https://api.platform.flowfinance.com.br/v1/loans
```

# Errors

This API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- You don't have persmission to access the requested resource.
404 | Not Found -- The resource could not be found.
405 | Method Not Allowed -- Invalid method.
406 | Not Acceptable -- You requested a format that isn't supported.
429 | Too Many Requests --  Too many requests in a given amount of time.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.


# Environments

We offers two environments for integration:

Sandbox: test environment, mirroring the logic and functionality of the production environment. Some minor configuration differences might be present with the production environment (e.g. account auto-approval) for enabling easier testing process.
Production: real environment, used for providing our services.


# Base URLs

* Sandbox - https://sandbox.platform.flowfinance.com.br
* Production - https://api.platform.flowfinance.com.br
