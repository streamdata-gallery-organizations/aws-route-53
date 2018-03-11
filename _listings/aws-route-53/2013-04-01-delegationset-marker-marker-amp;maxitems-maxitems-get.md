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
  /2013-04-01/delegationset?marker=Marker&amp;maxitems=MaxItems:
    get:
      summary: List Reusable Delegation Sets
      description: To retrieve a list of your reusable delegation sets, send a GET
        request tothe /2013-04-01/delegationset resource
      operationId: listreusabledelegationsets
      parameters:
      - in: path
        name: marker
        description: "If you're making the second or subsequent call to\t\t\t\tListReusableDelegationSets,
          the Marker element matches the value\t\t\tthat you specified in the marker
          parameter in the previous request"
        type: string
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