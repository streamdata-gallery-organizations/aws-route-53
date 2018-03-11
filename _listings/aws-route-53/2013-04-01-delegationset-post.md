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
  /2013-04-01/delegationset:
    post:
      summary: Create Reusable Delegation Set
      description: Creates a delegation set (a group of four name servers) that can
        be reused by multiplehosted zones
      operationId: createreusabledelegationset
      parameters:
      - in: body
        name: CallerReference
        description: "A unique string that identifies the request, and that allows
          you to retry failed\t\t\t\tCreateReusableDelegationSet requests without
          the risk of executing the\t\t\toperation twice"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateReusableDelegationSetRequest
        description: Root level tag for the CreateReusableDelegationSetRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: "If you want to mark the delegation set for an existing hosted
          zone as reusable, the ID\t\t\tfor that hosted zone"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - reusable delegation sets
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