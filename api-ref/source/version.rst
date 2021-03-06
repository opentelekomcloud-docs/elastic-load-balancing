===========
API Version
===========

Querying All API Versions
=========================

Function
^^^^^^^^

This API is used to query all API versions of ELB.

URI
^^^

GET /

Request
^^^^^^^

-  Request parameters

   None

-  Example request

   None

Response
^^^^^^^^

-  Response parameters

   .. table:: **Table 1** Parameter description

      +-------------+----------+---------------------------------------+
      | Parameter   | **Type** | Description                           |
      +=============+==========+=======================================+
      | versions    | Array    | Lists all API versions.               |
      +-------------+----------+---------------------------------------+
      | id          | String   | Specifies the version ID, for         |
      |             |          | example, **v1**.                      |
      +-------------+----------+---------------------------------------+
      | links       | Array    | Specifies the API URL.                |
      +-------------+----------+---------------------------------------+
      | href        | String   | Specifies the reference address of    |
      |             |          | the current API version.              |
      +-------------+----------+---------------------------------------+
      | rel         | String   | Specifies the relationship between    |
      |             |          | the current API version and the       |
      |             |          | referenced address.                   |
      +-------------+----------+---------------------------------------+
      | version     | String   | Specifies the version. If minor       |
      |             |          | versions are supported, set this      |
      |             |          | parameter to the latest minor         |
      |             |          | version. If minor versions are not    |
      |             |          | supported, leave this parameter       |
      |             |          | blank.                                |
      +-------------+----------+---------------------------------------+
      | status      | String   | Specifies the version status. Options |
      |             |          | are as follows:                       |
      |             |          |                                       |
      |             |          | -  **CURRENT**: indicates the major   |
      |             |          |    version.                           |
      |             |          | -  **SUPPORTED**: indicates that the  |
      |             |          |    version is an old one, but it is   |
      |             |          |    still supported.                   |
      |             |          | -  **DEPRECATED**: indicates a        |
      |             |          |    deprecated version which may be    |
      |             |          |    deleted later.                     |
      +-------------+----------+---------------------------------------+
      | updated     | String   | Specifies the version release time,   |
      |             |          | which must be the UTC time. For       |
      |             |          | example, the release time of v1 is    |
      |             |          | 2014-06-28T12:20:21Z.                 |
      +-------------+----------+---------------------------------------+
      | min_version | String   | Specifies the minor version. If minor |
      |             |          | versions are supported, set this      |
      |             |          | parameter to the earliest minor       |
      |             |          | version. If minor versions are not    |
      |             |          | supported, leave this parameter       |
      |             |          | blank.                                |
      +-------------+----------+---------------------------------------+

-  Example response

   .. code::

      {
         "versions": [
           {
             "id": "v1.0",
             "links": [
               {
                 "href": "https://{elb_endpoint}/v1.0/",
                 "rel": "self"
               }
             ],
             "min_version": "",
             "status": "CURRENT",
             "updated": "2018-09-30T00:00:00Z",
             "version": ""
           }
         ]
       }

Status Code
^^^^^^^^^^^

-  Normal

   200

-  Error

   =========== ===================== ====================================================================
   Status Code Message               Description
   =========== ===================== ====================================================================
   400         Bad Request           Request error.
   401         Unauthorized          The authentication information is not provided or is incorrect.
   403         Forbidden             The request was forbidden.
   404         Not Found             The requested resource does not exist.
   408         Request Timeout       The request timed out.
   429         Too Many Requests     The number requests exceeded the upper limit.
   500         Internal Server Error Failed to complete the request because of an internal service error.
   503         Service Unavailable   The service is currently unavailable.
   =========== ===================== ====================================================================

Querying a Specific API Version
===============================

Function
^^^^^^^^

This API is used to query a specific ELB API version.

URI
^^^

GET /{api_version}

.. table:: **Table 1** Parameter description

   =========== ============= ==========================
   Parameter   **Mandatory** Description
   =========== ============= ==========================
   api_version Yes           Specifies the API version.
   =========== ============= ==========================

-  **Example**

   /v1.0

Request
^^^^^^^

-  Request parameters

   None

-  Example request

   None

Response
^^^^^^^^

-  Response parameters

   .. table:: **Table 2** Response parameters

      +-------------+----------+---------------------------------------+
      | Parameter   | **Type** | Description                           |
      +=============+==========+=======================================+
      | version     | Object   | Specifies the API version.            |
      +-------------+----------+---------------------------------------+
      | id          | String   | Specifies the version ID, for         |
      |             |          | example, **v1**.                      |
      +-------------+----------+---------------------------------------+
      | links       | Array    | Specifies the API URL.                |
      +-------------+----------+---------------------------------------+
      | href        | String   | Specifies the reference address of    |
      |             |          | the current API version.              |
      +-------------+----------+---------------------------------------+
      | rel         | String   | Specifies the relationship between    |
      |             |          | the current API version and the       |
      |             |          | referenced address.                   |
      +-------------+----------+---------------------------------------+
      | version     | String   | Specifies the version. If minor       |
      |             |          | versions are supported, set this      |
      |             |          | parameter to the latest minor         |
      |             |          | version. If minor versions are not    |
      |             |          | supported, leave this parameter       |
      |             |          | blank.                                |
      +-------------+----------+---------------------------------------+
      | status      | String   | Specifies the version status. Options |
      |             |          | are as follows:                       |
      |             |          |                                       |
      |             |          | -  **CURRENT**: indicates the major   |
      |             |          |    version.                           |
      |             |          | -  **SUPPORTED**: indicates that the  |
      |             |          |    version is an old one, but it is   |
      |             |          |    still supported.                   |
      |             |          | -  **DEPRECATED**: indicates a        |
      |             |          |    deprecated version which may be    |
      |             |          |    deleted later.                     |
      +-------------+----------+---------------------------------------+
      | updated     | String   | Specifies the version release time,   |
      |             |          | which must be the UTC time. For       |
      |             |          | example, the release time of v1 is    |
      |             |          | 2014-06-28T12:20:21Z.                 |
      +-------------+----------+---------------------------------------+
      | min_version | String   | Specifies the minor version. If minor |
      |             |          | versions are supported, set this      |
      |             |          | parameter to the earliest minor       |
      |             |          | version. If minor versions are not    |
      |             |          | supported, leave this parameter       |
      |             |          | blank.                                |
      +-------------+----------+---------------------------------------+

-  Example response

   .. code::

      {
         "version": {
             "id": "v1.0",
             "links": [
               {
                 "href": "https://{elb_endpoint}/v1.0/",
                 "rel": "self"
               }
             ],
             "min_version": "",
             "status": "CURRENT",
             "updated": "2018-09-30T00:00:00Z",
             "version": ""
           }
       }

Status Code
^^^^^^^^^^^

-  Normal

   200

-  Error

   =========== ===================== ====================================================================
   Status Code Message               Description
   =========== ===================== ====================================================================
   400         Bad Request           Request error.
   401         Unauthorized          The authentication information is not provided or is incorrect.
   403         Forbidden             The request was forbidden.
   404         Not Found             The requested resource does not exist.
   408         Request Timeout       The request timed out.
   429         Too Many Requests     The number requests exceeded the upper limit.
   500         Internal Server Error Failed to complete the request because of an internal service error.
   503         Service Unavailable   The service is currently unavailable.
   =========== ===================== ====================================================================
