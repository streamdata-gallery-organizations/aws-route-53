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
  /2013-04-01/trafficpolicy/Id:
    post:
      summary: Create Traffic Policy Version
      description: Creates a new version of an existing traffic policy
      operationId: createtrafficpolicyversion
      parameters:
      - in: body
        name: Comment
        description: "The comment that you specified in the CreateTrafficPolicyVersion
          request,\t\t\tif any"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateTrafficPolicyVersionRequest
        description: Root level tag for the CreateTrafficPolicyVersionRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Document
        description: The definition of this version of the traffic policy, in JSON
          format
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: The ID of the traffic policy for which you want to create a new
          version
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