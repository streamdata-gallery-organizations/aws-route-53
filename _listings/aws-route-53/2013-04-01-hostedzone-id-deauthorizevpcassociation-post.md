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
  /2013-04-01/hostedzone/Id/deauthorizevpcassociation:
    post:
      summary: Delete V P C Association Authorization
      description: Removes authorization to submit an AssociateVPCWithHostedZone request
        to associate a specified VPC with a hosted zone that was created by a different
        account
      operationId: deletevpcassociationauthorization
      parameters:
      - in: body
        name: DeleteVPCAssociationAuthorizationRequest
        description: Root level tag for the DeleteVPCAssociationAuthorizationRequest
          parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: "When removing authorization to associate a VPC that was created
          by one AWS account with a hosted zone \t\t\tthat was created with a different
          AWS account, the ID of the hosted zone"
        type: string
      - in: body
        name: VPC
        description: "When removing authorization to associate a VPC that was created
          by one AWS account with a hosted zone \t\t\tthat was created with a different
          AWS account, a complex type that includes the ID and region of the VPC"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - vpc
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