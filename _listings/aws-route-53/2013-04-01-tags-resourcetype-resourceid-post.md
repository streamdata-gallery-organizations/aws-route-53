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
  /2013-04-01/tags/ResourceType/ResourceId:
    post:
      summary: Change Tags For Resource
      description: Adds, edits, or deletes tags for a health check or a hosted zone
      operationId: changetagsforresource
      parameters:
      - in: body
        name: AddTags
        description: "A complex type that contains a list of the tags that you want
          to add to the specified\t\t\thealth check or hosted zone and/or the tags
          for which you want to edit the Value\t\t\telement"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChangeTagsForResourceRequest
        description: Root level tag for the ChangeTagsForResourceRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: RemoveTagKeys
        description: "A complex type that contains a list of the tags that you want
          to delete from the\t\t\tspecified health check or hosted zone"
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: ResourceId
        description: The ID of the resource for which you want to add, change, or
          delete tags
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