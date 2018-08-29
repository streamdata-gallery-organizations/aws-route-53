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
  /2013-04-01/tags/ResourceType:
    post:
      summary: List Tags For Resources
      description: Lists tags for up to 10 health checks or hosted zones
      operationId: listtagsforresources
      parameters:
      - in: body
        name: ListTagsForResourcesRequest
        description: Root level tag for the ListTagsForResourcesRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ResourceIds
        description: "A complex type that contains the ResourceId element for each
          resource for which you\t\t\twant to get a list of tags"
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: ResourceType
        description: The type of the resources
        type: string
      responses:
        200:
          description: OK
      tags:
      - tags
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