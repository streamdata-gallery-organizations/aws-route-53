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
    post:
      summary: Update Health Check
      description: Updates an existing health check
      operationId: updatehealthcheck
      parameters:
      - in: body
        name: AlarmIdentifier
        description: "A complex type that identifies the CloudWatch alarm that you
          want Amazon Route 53 health checkers to\t\t\tuse to determine whether this
          health check is healthy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChildHealthChecks
        description: "A complex type that contains one ChildHealthCheck element for
          each health\t\t\tcheck that you want to associate with a CALCULATED health
          check"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: EnableSNI
        description: "Specify whether you want Amazon Route 53 to send the value of\t\t\t\tFullyQualifiedDomainName
          to the endpoint in the client_hello\t\t\tmessage during TLS negotiation"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FailureThreshold
        description: "The number of consecutive health checks that an endpoint must
          pass or fail for Amazon Route 53 to\t\t\tchange the current status of the
          endpoint from unhealthy to healthy or vice versa"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FullyQualifiedDomainName
        description: Amazon Route 53 behavior depends on whether you specify a value
          for IPAddress
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want detailed information
        type: string
      - in: body
        name: HealthCheckVersion
        description: "A sequential counter that Amazon Route 53 sets to 1 when you
          create a health check\t\t\tand increments by 1 each time you update settings
          for the health check"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HealthThreshold
        description: "The number of child health checks that are associated with a
          CALCULATED\t\t\thealth that Amazon Route 53 must consider healthy for the
          CALCULATED health check to be\t\t\tconsidered healthy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: InsufficientDataHealthStatus
        description: "When CloudWatch has insufficient data about the metric to determine
          the alarm state, the status \t\t\tthat you want Amazon Route 53 to assign
          to the health check:                        Healthy: Amazon Route 53 considers
          the health check to be healthy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Inverted
        description: "Specify whether you want Amazon Route 53 to invert the status
          of a health check, for example, to\t\t\tconsider a health check unhealthy
          when it otherwise would be considered healthy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: IPAddress
        description: The IPv4 or IPv6 IP address for the endpoint that you want Amazon
          Route 53 to perform health checks on
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Port
        description: The port on the endpoint on which you want Amazon Route 53 to
          perform health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Regions
        description: "A complex type that contains one Region element for each region
          from which you want\t\t\tAmazon Route 53 health checkers to check the specified
          endpoint"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ResourcePath
        description: The path that you want Amazon Route 53 to request when performing
          health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: SearchString
        description: "If the value of Type is HTTP_STR_MATCH or\t\t\t\tHTTP_STR_MATCH,
          the string that you want Amazon Route 53 to search for in the response\t\t\tbody
          from the specified resource"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: UpdateHealthCheckRequest
        description: Root level tag for the UpdateHealthCheckRequest parameters
        schema:
          $ref: '#/definitions/holder'
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