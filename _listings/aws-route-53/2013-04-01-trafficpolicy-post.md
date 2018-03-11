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
  /2013-04-01/trafficpolicy:
    post:
      summary: Create Traffic Policy
      description: Creates a traffic policy, which you use to create multiple DNS
        resource record sets forone domain name (such as example
      operationId: createtrafficpolicy
      parameters:
      - in: body
        name: Comment
        description: (Optional) Any comments that you want to include about the traffic
          policy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateTrafficPolicyRequest
        description: Root level tag for the CreateTrafficPolicyRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Document
        description: The definition of this traffic policy in JSON format
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The name of the traffic policy
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