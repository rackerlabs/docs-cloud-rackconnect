.. _common-dg-status:

Status codes
~~~~~~~~~~~~

When you send an API request to a Rackspace Cloud service, the service returns an
object containing an HTTP status code the denotes the response. The response body
returns additional information about the status code.

HTTP status codes come in different classes. Classes are determined by the first
digit of the status code:

 - 2xx (Success)
 - 4xx (Client error)
 - 5xx (Server error)

.. note::
   HTTP status codes are not standard across all Rackspace Cloud services.
   The same code could have multiple response types. Read the response body
   carefully to accurately the determine the nature of the response.

.. note::
   For a more comprehensive list of HTTP status codes, refer to `RFC-7231`_.

.. _RFC-7231: http://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml

.. _common-dg-status-body:

Response body
^^^^^^^^^^^^^

The response body of HTTP status codes varies by service and type. Responses may contain
some or all of these elements:

- *title*

- ``type``

- ``code``

- ``message``

- ``details``

.. note::
   Elements such as ``type``, ``message``, and ``details`` only appear with 4xx (Client error)
   and 5xx (Server Error) status codes.

**Example: Error message syntax**

.. code::

   { "error": {
    "type": "failure type",
    "code": HTTP status code,
    "message": "detailed message",
    "details": "any specific details about the error"
    }
   }

.. _common-dg-status-two:

2xx status codes
^^^^^^^^^^^^^^^^

The 2xx class status code confirms that a request has succeeded.

The following table lists possible 2xx status codes with their associated
descriptions:

  **Table: 2xx status codes**

  +-------------+----------------------------+---------------------------------+
  | Status code | Response                   | Description                     |
  +=============+============================+=================================+
  | 200         | ``OK``                     | The request has succeeded.      |
  |             |                            | (Some API calls might return    |
  |             |                            | 201 instead.)                   |
  +-------------+----------------------------+---------------------------------+
  | 201         | ``Created``                | The request has been fulfilled  |
  |             |                            | and a new resource was created. |
  +-------------+----------------------------+---------------------------------+
  | 202         | ``Accepted``               | The request has been accepted   |
  |             |                            | for processing.                 |
  +-------------+----------------------------+---------------------------------+
  | 204         | ``No Content``             | No additional content sent to   |
  |             |                            | response body despite the       |
  |             |                            | request being filled.           |
  +-------------+----------------------------+---------------------------------+

.. _common-dg-status-two-example:

The following examples show basic ``200 OK`` request. Since the request succeeded,
no ``type``, ``message``, or ``details`` elements are contained in the response
body:

**Example: basic success response, XML**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/xml
    Content-Length: 455

    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <asyncresponse xmlns:ns2="http://www.w3.org/2005/Atom" xmlns="http://docs.rackspacecloud.com/dns/api/v1.0" xmlns:ns3="http://docs.rackspacecloud.com/dns/api/management/v1.0">
        <jobId>3593a5e9-83af-4eb8-ae1a-25f07b747d80</jobId>
        <callbackUrl>https://dns.api.rackspacecloud.com/v1.0/1234/status/3593a5e9-83af-4eb8-ae1a-25f07b747d80</callbackUrl>
        <status>COMPLETED</status>
    </asyncresponse>


**Example: basic success response, JSON**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/json
    Content-Length: 190

    {
      "status" : "COMPLETED",
      "jobId" : "3593a5e9-83af-4eb8-ae1a-25f07b747d80",
      "callbackUrl" : "https://dns.api.rackspacecloud.com/v1.0/1234/status/3593a5e9-83af-4eb8-ae1a-25f07b747d80"
    }

.. _common-dg-status-four:

4xx status codes
^^^^^^^^^^^^^^^^

The 4xx class status code indicates that a request contains errors or cannot
be fulfilled.

The following table lists possible 4xx status codes with their associated
descriptions:

  **Table: 4xx status codes**

  +-------------+-----------------------------+--------------------------------+
  | Status code | Response                    | Description                    |
  +=============+=============================+================================+
  | 400         | ``badRequest``              | There was one or more errors   |
  |             |                             | in the user request.           |
  +-------------+-----------------------------+--------------------------------+
  | 401         | ``unauthorized``            | The supplied token is not      |
  |             |                             | authorized to access the       |
  |             |                             | resources, either it's         |
  |             |                             | expired or invalid.            |
  +-------------+-----------------------------+--------------------------------+
  | 403         | ``forbidden``               | Access to the requested        |
  |             |                             | resource was denied.           |
  +-------------+-----------------------------+--------------------------------+
  | 404         | ``Not Found``               | The back-end services did not  |
  |             |                             | find anything matching the     |
  |             |                             | request-URI.                   |
  +-------------+-----------------------------+--------------------------------+
  | 405         | ``badMethod``               | The requested method is not    |
  |             |                             | allowed for this resource.     |
  +-------------+-----------------------------+--------------------------------+
  | 412         | ``invalidImage``            | This fault is related to       |
  |             |                             | creating volumes for the boot  |
  |             |                             | from volume feature. The       |
  |             |                             | uncompressed image size must   |
  |             |                             | be 127 GB or less.             |
  +-------------+-----------------------------+--------------------------------+
  | 413         | ``overLimit``               | Either the number of entities  |
  |             |                             | in the request is larger than  |
  |             |                             | allowed limits, or the user    |
  |             |                             | has exceeded allowable         |
  |             |                             | request rate limits. See the   |
  |             |                             | details element for more       |
  |             |                             | specifics. Contact support if  |
  |             |                             | you think you need higher      |
  |             |                             | request rate limits.           |
  +-------------+-----------------------------+--------------------------------+
  | 415         | ``badMediaType``            | The requested content type is  |
  |             |                             | not supported by this service  |
  +-------------+-----------------------------+--------------------------------+
  | 422         |``unprocessableEntity``      | The requested resource could   |
  |             |                             | not be processed on at the     |
  |             |                             | moment.                        |
  +-------------+-----------------------------+--------------------------------+

.. _common-dg-status-four-example:

The following ``badRequest`` examples show errors when the volume size of a request
is invalid.

**Example: badRequest fault on volume size errors, XML**

.. code::

    HTTP/1.1 400 None
    Content-Type: application/xml
    Content-Length: 121
    Date: Mon, 28 Nov 2011 18:19:37 GMT

.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <badRequest code="400" xmlns="http://docs.rackspace.com/cbs/api/v1.0">
        <message> Volume 'size' needs to be a positive integer value, -1.0
            cannot be accepted. </message>
    </badRequest>

**Example: badRequest fault on volume size errors, JSON**

.. code::

    HTTP/1.1 400 None
    Content-Length: 120
    Content-Type: application/json; charset=UTF-8
    Date: Tue, 29 Nov 2011 00:33:48 GMT

.. code::

    {
       "badRequest":{
          "code":400,
          "message":"Volume 'size' needs to be a positive integer value, -1.0 cannot be accepted."
       }
    }

.. _common-dg-status-five:

5xx status codes
^^^^^^^^^^^^^^^^

The 5xx status code indicates that a request cannot be fulfilled because the
server has encountered an error.

The following table lists possible 5xx status codes with their associated
descriptions:

  **Table: 5xx status codes**

  +-------------+------------------------+-------------------------------------+
  | Status code | Response               | Description                         |
  +-------------+------------------------+-------------------------------------+
  | 500         | ``instanceFault``      | This is a generic server error and  |
  |             |                        | the message contains the reason     |
  |             |                        | for this error. This error could    |
  |             |                        | error could wrap several error      |
  |             |                        | messages and is a catch all.        |
  +-------------+------------------------+-------------------------------------+
  | 501         | ``notImplemented``     | The requested method or resource    |
  |             |                        | is not implemented.                 |
  +-------------+------------------------+-------------------------------------+
  | 503         | ``serviceUnavailable`` | The request has been accepted       |
  |             |                        | for processing.                     |
  +-------------+------------------------+-------------------------------------+

.. _common-dg-status-five-example:

The following ``instanceFault`` examples show errors when the server has
erred or cannot perform the requested operation.

**Example: instanceFault response, XML**

.. code::

    HTTP/1.1 500 Internal Server Error
    Content-Type: application/xml
    Content-Length: 121
    Date: Mon, 28 Jun 2015 18:19:37 GMT

.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <instanceFault code="500"
        xmlns="http://docs.rackspace.com/cbs/api/v1.0">
        <message> The server has either erred or is incapable of
            performing the requested operation. </message>
    </instanceFault>


**Example: instanceFault response, JSON**

.. code::

    HTTP/1.1 500 Internal Server Error
    Content-Length: 120
    Content-Type: application/json; charset=UTF-8
    Date: Tue, 29 Jun 2015 00:33:48 GMT

.. code::

    {
       "instance_fault":{
          "code":500,
          "message":"The server has either erred or is incapable of performing the requested operation."
       }
    }

.. _common-dg-status-synch:

Synchronous versus asynchronous responses
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Synchronous**

*Synchronous* responses occur at request time. Synchronous responses contains all or some
of same elements as found in the :ref:`response body <common-dg-status-body>` attached
to an HTTP status code.

**GET** requests often return *synchronous* responses, since the request is always
retrieving existing information.

.. _common-dg-status-aynch:

**Asynchronous**

*Asynchronous* responses occur in the background while an instance, database, or
user is being built or an instance is executing an action.

**PUT**, **POST**, and **DELETE** requests return *asynchronous* responses. These
responses take some time to process. Therefore an *asynchronous* response return
``202 Accepted`` responses containing information with a callback URL, which allows the progress,
status, and/or response information of the call to be retrieved at a later point in time.

When an asynchronous request returns an error, the system places the instance, database,
or user in an ERROR state and embeds the fault in the offending instance, database, or user.

Asynchronous responses contain these elements:

**Attributes for asynchronous responses**

jobId
   An identifier for the specific request.
   Inclusion: Basic and Detail

callbackUrl
   Resource locator for querying the status of the request.
   Inclusion: Basic and Detail

status
   An indicator of the request status: INITIALIZED, RUNNING, COMPLETED, or
   ERROR.
   Inclusion: Basic and Detail

.. note::
   INITIALIZED is the status that immediately precedes RUNNING and is
   the first possible state of a job. It indicates acceptance of the job.

requestUrl
   The url of the original request.
   Inclusion: Detail only

verb
   The type of the original request: PUT, POST, or DELETE.
   Inclusion: Detail only

request
   The original request data, if any.
   Inclusion: Detail only

response
   The results of a COMPLETE operation, if any.
   Inclusion: Detail only

error
   The results of an ERROR operation.
   Inclusion: Detail only

..  note::
    Note that an asynchronous operation, if it fails, may not give the user an error,
    and the operation can error out without a failure notification.

The asynchronous response body will look similar to the following
examples, depending on whether basic or detailed information is
requested.

If an error occurs as a result of processing the original request,
querying the callback URL will return the information about the error.
If you use the callback URL without specifying the query parameter
``showDetails=true``, only basic information is provided:

.. _common-dg-status-async-example:

**Example: Basic error asynchronous response, XML**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/xml
    Content-Length: 451

    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <asyncresponse xmlns:ns2="http://www.w3.org/2005/Atom" xmlns="http://docs.rackspacecloud.com/dns/api/v1.0" xmlns:ns3="http://docs.rackspacecloud.com/dns/api/management/v1.0">
        <jobId>e63886c9-acf0-4e5d-8023-09a0fae37446</jobId>
        <callbackUrl>https://dns.api.rackspacecloud.com/v1.0/1234/status/e63886c9-acf0-4e5d-8023-09a0fae37446</callbackUrl>
        <status>ERROR</status>
    </asyncresponse>

**Example: Basic error asynchronous response, JSON**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/json
    Content-Length: 186

    {
      "status" : "ERROR",
      "jobId" : "e63886c9-acf0-4e5d-8023-09a0fae37446",
      "callbackUrl" : "https://dns.api.rackspacecloud.com/v1.0/1234/status/e63886c9-acf0-4e5d-8023-09a0fae37446"
    }

If you use the callback URL with the query parameter
``showDetails=true``, then detailed information is provided:

**Example: Detail error asynchronous response, XML**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/xml
    Content-Length: 847

    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <asyncresponse xmlns:ns2="http://www.w3.org/2005/Atom" xmlns="http://docs.rackspacecloud.com/dns/api/v1.0" xmlns:ns3="http://docs.rackspacecloud.com/dns/api/management/v1.0">
        <jobId>e63886c9-acf0-4e5d-8023-09a0fae37446</jobId>
        <callbackUrl>https://dns.api.rackspacecloud.com/v1.0/1234/status/e63886c9-acf0-4e5d-8023-09a0fae37446</callbackUrl>
        <status>ERROR</status>
        <requestUrl>https://dns.api.rackspacecloud.com/v1.0/1234/domains</requestUrl>
        <verb>POST</verb>
        <request>{
            "domains" : [ {
            "name" : "example.com",
            "emailAddress" : "admin@example.com"
            } ]
            }
        </request>
        <error code="409">
            <message>The object already exists.</message>
            <details>Domain already exists</details>
        </error>
    </asyncresponse>

**Example: Detail error asynchronous response, JSON**

.. code::

    Status: 200 OK
    Date: Thu, 28 Jul 2011 21:54:21 GMT
    X-API-VERSION: 1.0.17
    Content-Type: application/json
    Content-Length: 564

    {
      "status" : "ERROR",
      "error" : {
        "message" : "The object already exists.",
        "code" : 409,
        "details" : "Domain already exists"
      },
      "request" : "{\n        \"domains\" : [ {\n        \"name\" : \"example.com\",\n        \"emailAddress\" : \"admin@example.com\"\n        } ]\n        }\n    ",
      "verb" : "POST",
      "jobId" : "e63886c9-acf0-4e5d-8023-09a0fae37446",
      "callbackUrl" : "https://dns.api.rackspacecloud.com/v1.0/1234/status/e63886c9-acf0-4e5d-8023-09a0fae37446",
      "requestUrl" : "https://dns.api.rackspacecloud.com/v1.0/1234/domains"
    }
