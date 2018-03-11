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
  /2013-04-01/trafficpolicy/Id/Version:
    post:
      summary: Update Traffic Policy Comment
      description: Updates the comment for a specified traffic policy version
      operationId: updatetrafficpolicycomment
      parameters:
      - in: body
        name: Comment
        description: The new comment for the specified traffic policy and version
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: "The value of Id for the traffic policy for which you want to
          update the\t\t\tcomment"
        type: string
      - in: body
        name: UpdateTrafficPolicyCommentRequest
        description: Root level tag for the UpdateTrafficPolicyCommentRequest parameters
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