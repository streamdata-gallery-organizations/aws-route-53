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
  /2013-04-01/trafficpolicyinstance:
    post:
      summary: Create Traffic Policy Instance
      description: Creates resource record sets in a specified hosted zone based on
        the settings in aspecified traffic policy version
      operationId: createtrafficpolicyinstance
      parameters:
      - in: body
        name: CreateTrafficPolicyInstanceRequest
        description: Root level tag for the CreateTrafficPolicyInstanceRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: "The ID of the hosted zone in which you want Amazon Route 53
          to create resource record sets by\t\t\tusing the configuration in a traffic
          policy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The domain name (such as example
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TrafficPolicyId
        description: "The ID of the traffic policy that you want to use to create
          resource record sets in the\t\t\tspecified hosted zone"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TrafficPolicyVersion
        description: "The version of the traffic policy that you want to use to create
          resource record sets\t\t\tin the specified hosted zone"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TTL
        description: "(Optional) The TTL that you want Amazon Route 53 to assign to
          all of the resource record sets\t\t\tthat it creates in the specified hosted
          zone"
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