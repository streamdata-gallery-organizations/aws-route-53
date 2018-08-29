---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API Associate V P C With Hosted Zone
  version: 1.0.0
  description: Associates an Amazon VPC with a private hosted zone. ImportantTo perform
    the association, the VPC and the private hosted zone must already exist. You can't
    convert a public hosted zone into a private hosted zone.Send a POST request to
    the /2013-04-01/hostedzone/hosted zone ID/associatevpc resource. The request body
    must include a document with an AssociateVPCWithHostedZoneRequest element. The
    response contains a ChangeInfo data type that you can use to track the progress
    of the request. NoteIf you want to associate a VPC that was created by using one
    AWS account with a private hosted zone that was created by using a different account,
    the AWS account that created the private hosted zone must first submit a CreateVPCAssociationAuthorization
    request. Then the account that created the VPC must submit an AssociateVPCWithHostedZone
    request.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2013-04-01/hostedzone/Id/associatevpc:
    post:
      summary: Associate V P C With Hosted Zone
      description: Associates an Amazon VPC with a private hosted zone. ImportantTo
        perform the association, the VPC and the private hosted zone must already
        exist. You can't convert a public hosted zone into a private hosted zone.Send
        a POST request to the /2013-04-01/hostedzone/hosted zone ID/associatevpc resource.
        The request body must include a document with an AssociateVPCWithHostedZoneRequest
        element. The response contains a ChangeInfo data type that you can use to
        track the progress of the request. NoteIf you want to associate a VPC that
        was created by using one AWS account with a private hosted zone that was created
        by using a different account, the AWS account that created the private hosted
        zone must first submit a CreateVPCAssociationAuthorization request. Then the
        account that created the VPC must submit an AssociateVPCWithHostedZone request.
      operationId: associatevpcwithhostedzone
      x-api-path-slug: 20130401hostedzoneidassociatevpc-post
      parameters:
      - in: body
        name: AssociateVPCWithHostedZoneRequest
        description: Root level tag for the AssociateVPCWithHostedZoneRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Comment
        description: 'Optional: A comment about the association request'
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: The ID of the private hosted zone that you want to associate
          an Amazon VPC with
        type: string
      - in: body
        name: VPC
        description: A complex type that contains information about the VPC that you
          want to associate with a private hosted zone
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - VPC
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