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
  ? /2013-04-01/trafficpolicyinstances/trafficpolicy&amp;hostedzoneid=HostedZoneIdMarker?id=TrafficPolicyId&amp;maxitems=MaxItems&amp;trafficpolicyinstancename=TrafficPolicyInstanceNameMarker&amp;trafficpolicyinstancetype=TrafficPolicyInstanceTypeMarker&
  : get:
      summary: List Traffic Policy Instances By Policy
      description: Gets information about the traffic policy instances that you created
        by using a specifytraffic policy version
      operationId: listtrafficpolicyinstancesbypolicy
      parameters:
      - in: query
        name: CapacityId
        description: The ID that identifies the provisioned capacity unit
        type: string
      - in: query
        name: ExpirationDate
        description: The date that the provisioned capacity unit expires, in Coordinated                            Universal
          Time (UTC)
        type: string
      - in: path
        name: hostedzoneid
        description: "For the first request to ListTrafficPolicyInstancesByPolicy,
          omit this\t\t\tvalue"
        type: string
      - in: query
        name: StartDate
        description: The date that the provisioned capacity unit was purchased, in
          Coordinated                            Universal Time (UTC)
        type: string
      - in: query
        name: TagKeys
        description: A list of tag keys
        type: string
      - in: query
        name: Tags
        description: The tags attached to the vault
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