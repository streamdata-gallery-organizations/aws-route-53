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
  /2013-04-01/trafficpolicies&amp;maxitems=MaxItems?trafficpolicyid=TrafficPolicyIdMarker:
    get:
      summary: List Traffic Policies
      description: Gets information about the latest version for every traffic policy
        that is associatedwith the current AWS account
      operationId: listtrafficpolicies
      parameters:
      - in: path
        name: maxitems
        description: "(Optional) The maximum number of traffic policies to be included
          in the response body\t\t\tfor this request"
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