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
  /2013-04-01/hostedzonesbyname?dnsname=DNSName&amp;hostedzoneid=HostedZoneId&amp;maxitems=MaxItems:
    get:
      summary: List Hosted Zones By Name
      description: Retrieves a list of your hosted zones in lexicographic order
      operationId: listhostedzonesbyname
      parameters:
      - in: path
        name: dnsname
        description: "(Optional) For your first request to ListHostedZonesByName,
          include the\t\t\t\tdnsname parameter only if you want to specify the name
          of the first hosted zone\t\t\tin the response"
        type: string
      responses:
        200:
          description: OK
      tags:
      - hosted zones
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