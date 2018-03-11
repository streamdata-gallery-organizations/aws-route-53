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
  /2013-04-01/healthcheck/HealthCheckId:
    get:
      summary: Get Health Check
      description: Gets information about a specified health check
      operationId: gethealthcheck
      parameters:
      - in: path
        name: HealthCheckId
        description: The identifier that Amazon Route 53 assigned to the health check
          when you created it
        type: string
      responses:
        200:
          description: OK
      tags:
      - health checks
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