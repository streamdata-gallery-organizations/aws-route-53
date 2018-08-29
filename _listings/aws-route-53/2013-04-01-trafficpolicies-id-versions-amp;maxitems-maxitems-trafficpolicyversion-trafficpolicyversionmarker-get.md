---
swagger: "2.0"
info:
  title: AWS Route 53 API
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2013-04-01/trafficpolicies/Id/versions&amp;maxitems=MaxItems?trafficpolicyversion=TrafficPolicyVersionMarker:
    get:
      summary: List Traffic Policy Versions
      description: Gets information about all of the versions for a specified traffic
        policy
      operationId: listtrafficpolicyversions
      parameters:
      - in: path
        name: Id
        description: "Specify the value of Id of the traffic policy for which you
          want to list\t\t\tall versions"
        type: string
      responses:
        200:
          description: OK
      tags:
      - traffic policies
definitions: []
x-collection-name: AWS Route 53
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---