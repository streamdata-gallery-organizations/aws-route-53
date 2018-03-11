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
  /2013-04-01/trafficpolicyinstance/Id:
    post:
      summary: Update Traffic Policy Instance
      description: Updates the resource record sets in a specified hosted zone that
        were created based onthe settings in a specified traffic policy version
      operationId: updatetrafficpolicyinstance
      parameters:
      - in: path
        name: Id
        description: The ID of the traffic policy instance that you want to update
        type: string
      - in: body
        name: TrafficPolicyId
        description: "The ID of the traffic policy that you want Amazon Route 53 to
          use to update resource record sets\t\t\tfor the specified traffic policy
          instance"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TrafficPolicyVersion
        description: "The version of the traffic policy that you want Amazon Route
          53 to use to update resource record\t\t\tsets for the specified traffic
          policy instance"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TTL
        description: "The TTL that you want Amazon Route 53 to assign to all of the
          updated resource record\t\t\tsets"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: UpdateTrafficPolicyInstanceRequest
        description: Root level tag for the UpdateTrafficPolicyInstanceRequest parameters
        schema:
          $ref: '#/definitions/holder'
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