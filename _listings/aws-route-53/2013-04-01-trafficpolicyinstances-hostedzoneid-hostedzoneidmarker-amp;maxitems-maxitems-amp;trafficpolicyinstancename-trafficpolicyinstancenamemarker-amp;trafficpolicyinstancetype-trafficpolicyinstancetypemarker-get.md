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
  ? /2013-04-01/trafficpolicyinstances?hostedzoneid=HostedZoneIdMarker&amp;maxitems=MaxItems&amp;trafficpolicyinstancename=TrafficPolicyInstanceNameMarker&amp;trafficpolicyinstancetype=TrafficPolicyInstanceTypeMarker
  : get:
      summary: List Traffic Policy Instances
      description: Gets information about the traffic policy instances that you created
        by using thecurrent AWS account
      operationId: listtrafficpolicyinstances
      parameters:
      - in: path
        name: hostedzoneid
        description: "For the first request to ListTrafficPolicyInstances, omit this\t\t\tvalue"
        type: string
      responses:
        200:
          description: OK
      tags:
      - traffic policies
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