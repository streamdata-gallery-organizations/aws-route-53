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
  /2013-04-01/healthcheck/HealthCheckId/lastfailurereason:
    get:
      summary: Get Health Check Last Failure Reason
      description: If you want to learn why a health check is currently failing or
        why it failed mostrecently (if at all), you can get the failure reason for
        the most recent failure
      operationId: gethealthchecklastfailurereason
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want the last failure
          reason
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