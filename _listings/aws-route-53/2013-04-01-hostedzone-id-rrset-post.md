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
  /2013-04-01/hostedzone/Id/rrset/:
    post:
      summary: Change Resource Record Sets
      description: Create, change, update, or delete authoritative DNS information
        on all Amazon Route 53 servers
      operationId: changeresourcerecordsets
      parameters:
      - in: body
        name: ChangeBatch
        description: "A complex type that contains an optional comment and the Changes\t\t\telement"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChangeResourceRecordSetsRequest
        description: Root level tag for the ChangeResourceRecordSetsRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: "The ID of the hosted zone that contains the resource record
          sets that you want to\t\t\tchange"
        type: string
      responses:
        200:
          description: OK
      tags:
      - changes
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