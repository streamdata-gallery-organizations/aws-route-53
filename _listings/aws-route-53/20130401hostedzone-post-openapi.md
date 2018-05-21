---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API Create Hosted Zone
  version: 1.0.0
  description: Creates a new public hosted zone, used to specify how the Domain Name
    System (DNS)routes traffic on the Internet for a domain, such as example.com,
    and its subdomains. ImportantPublic hosted zones can't be converted to a private
    hosted zone or vice versa.Instead, create a new hosted zone with the same name
    and create new resource recordsets.Send a POST request to the /2013-04-01/hostedzone
    resource. The request body must include a documentwith a CreateHostedZoneRequest
    element. The response returns theCreateHostedZoneResponse element containing metadata
    about the hostedzone.Fore more information about charges for hosted zones, see
    Amazon Route 53 Pricing.Note the following:You can't create a hosted zone for
    a top-level domain (TLD).Amazon Route 53 automatically creates a default SOA record
    and four NS records for the zone.For more information about SOA and NS records,
    see NS and SOA Records that Amazon Route 53 Creates for a Hosted Zone in the Amazon
    Route 53 Developer Guide.If your domain is registered with a registrar other than
    Amazon Route 53, you must update thename servers with your registrar to make Amazon
    Route 53 your DNS service. For more information, seeConfiguring Amazon Route 53
    as your DNSService in the Amazon Route 53 Developer's Guide.After creating a zone,
    its initial status is PENDING. This means that itis not yet available on all DNS
    servers. The status of the zone changes to INSYNCwhen the NS and SOA records are
    available on all Amazon Route 53 DNS servers. When trying to create a hosted zone
    using a reusable delegation set, specify anoptional DelegationSetId, and Amazon
    Route 53 would assign those 4 NS records for the zone, instead ofallotting a new
    one.
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
  /2013-04-01/hostedzone/Id/rrset/:
    post:
      summary: Change Resource Record Sets
      description: 'Create, change, update, or delete authoritative DNS information
        on all Amazon Route 53 servers.Send a POST request to:             /2013-04-01/hostedzone/Amazon
        Route 53 hosted ZoneID/rrset resource. The request body must include a document
        with aChangeResourceRecordSetsRequest element. The request body contains a
        list ofchange items, known as a change batch. Change batches are considered
        transactional changes.When using the Amazon Route 53 API to change resource
        record sets, Amazon Route 53 either makes all or none of thechanges in a change
        batch request. This ensures that Amazon Route 53 never partially implements
        theintended changes to the resource record sets in a hosted zone. For example,
        a change batch request that deletes the CNAME record forwww.example.com and
        creates an alias resource record set for www.example.com. Amazon Route 53
        deletesthe first resource record set and creates the second resource record
        set in a singleoperation. If either the DELETE or the CREATE action fails,
        thenboth changes (plus any other changes in the batch) fail, and the original
        CNAMErecord continues to exist.ImportantDue to the nature of transactional
        changes, you can''t delete the same resourcerecord set more than once in a
        single change batch. If you attempt to delete the same changebatch more than
        once, Amazon Route 53 returns an InvalidChangeBatch error.NoteTo create resource
        record sets for complex routing configurations, use either thetraffic flow
        visual editor in the Amazon Route 53 console or the API actions for traffic
        policies andtraffic policy instances. Save the configuration as a traffic
        policy, then associate thetraffic policy with one or more domain names (such
        as example.com) or subdomain names (suchas www.example.com), in the same hosted
        zone or in multiple hosted zones. You can roll backthe updates if the new
        configuration isn''t performing as expected. For more information, seeUsing
        Traffic Flow to Route DNSTraffic in the Amazon Route 53 Developer Guide.Use
        ChangeResourceRecordsSetsRequest to perform the following actions:                  CREATE:
        Creates a resource record set that has the specified values.                  DELETE:
        Deletes an existing resource record set that has the specified values.                  UPSERT:
        If a resource record set does not already exist, AWS createsit. If a resource
        set does exist, Amazon Route 53 updates it with the values in the request.
        The values that you need to include in the request depend on the type of resource
        record set that you''re creating, deleting, or updating:            Basic
        resource record sets (excluding alias, failover, geolocation, latency, and
        weighted resource record sets)                           Name                                 Type                                 TTL                           Failover,
        geolocation, latency, or weighted resource record sets (excluding alias resource
        record sets)                           Name                                 Type                                 TTL                                 SetIdentifier                           Alias
        resource record sets (including failover alias, geolocation alias, latency
        alias, and weighted alias resource record sets)                           Name                                 Type                                 AliasTarget
        (includes DNSName, EvaluateTargetHealth, and HostedZoneId)                  SetIdentifier
        (for failover, geolocation, latency, and weighted resource record sets)When
        you submit a ChangeResourceRecordSets request, Amazon Route 53 propagates
        your changes to all of the Amazon Route 53 authoritative DNS servers. While
        your changes are propagating, GetChange returns a status of PENDING. When
        propagation is complete, GetChange returns a status of INSYNC. Changes generally
        propagate to all Amazon Route 53 name servers in a few minutes. In rare circumstances,
        propagation can take up to 30 minutes. For more information, see GetChange       For
        information about the limits on a ChangeResourceRecordSets request, see Limits
        in the Amazon Route 53 Developer Guide.'
      operationId: changeresourcerecordsets
      x-api-path-slug: 20130401hostedzoneidrrset-post
      parameters:
      - in: body
        name: ChangeBatch
        description: "A complex type that contains an optional comment and the Changes\t\t\telement"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChangeResourceRecordSetsRequest
        description: Root level tag for the ChangeResourceRecordSetsRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: "The ID of the hosted zone that contains the resource record
          sets that you want to\t\t\tchange"
        type: string
      responses:
        200:
          description: OK
      tags:
      - Changes
  /2013-04-01/tags/ResourceType/ResourceId:
    post:
      summary: Change Tags For Resource
      description: Adds, edits, or deletes tags for a health check or a hosted zone.For
        information about using tags for cost allocation, see Using Cost Allocation
        Tags in the AWS Billing and Cost Management User Guide.
      operationId: changetagsforresource
      x-api-path-slug: 20130401tagsresourcetyperesourceid-post
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
      - Changes
  /2013-04-01/healthcheck:
    post:
      summary: Create Health Check
      description: Creates a new health check.To create a new health check, send a
        POST request to the/2013-04-01/healthcheck resource. The request body must
        include a documentwith a CreateHealthCheckRequest element. The response returns
        theCreateHealthCheckResponse element, containing the health check ID specifiedwhen
        adding health check to a resource record set. For information about adding
        health checksto resource record sets, see ResourceRecordSet:HealthCheckId
        in ChangeResourceRecordSets. If you are registering EC2 instances with an
        Elastic Load Balancing (ELB) loadbalancer, do not create Amazon Route 53 health
        checks for the EC2 instances. When you register anEC2 instance with a load
        balancer, you configure settings for an ELB health check, whichperforms a
        similar function to an Amazon Route 53 health check.You can associate health
        checks with failover resource record sets in a private hostedzone. Note the
        following:Amazon Route 53 health checkers are outside the VPC. To check the
        health of an endpointwithin a VPC by IP address, you must assign a public
        IP address to the instance in theVPC.You can configure a health checker to
        check the health of an external resource thatthe instance relies on, such
        as a database server.You can create a CloudWatch metric, associate an alarm
        with the metric, and then create ahealth check that is based on the state
        of the alarm. For example, you might create a CloudWatchmetric that checks
        the status of the Amazon EC2 StatusCheckFailed metric, add analarm to the
        metric, and then create a health check that is based on the state of thealarm.
        For information about creating CloudWatch metrics and alarms by using the
        CloudWatch console,see the Amazon CloudWatch User Guide.
      operationId: createhealthcheck
      x-api-path-slug: 20130401healthcheck-post
      parameters:
      - in: body
        name: CallerReference
        description: "A unique string that identifies the request and that allows
          failed\t\t\t\tCreateHealthCheck requests to be retried without the risk
          of executing the\t\t\toperation twice"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateHealthCheckRequest
        description: Root level tag for the CreateHealthCheckRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HealthCheckConfig
        description: A complex type that contains the response to a CreateHealthCheck
          request
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/hostedzone:
    post:
      summary: Create Hosted Zone
      description: Creates a new public hosted zone, used to specify how the Domain
        Name System (DNS)routes traffic on the Internet for a domain, such as example.com,
        and its subdomains. ImportantPublic hosted zones can't be converted to a private
        hosted zone or vice versa.Instead, create a new hosted zone with the same
        name and create new resource recordsets.Send a POST request to the /2013-04-01/hostedzone
        resource. The request body must include a documentwith a CreateHostedZoneRequest
        element. The response returns theCreateHostedZoneResponse element containing
        metadata about the hostedzone.Fore more information about charges for hosted
        zones, see Amazon Route 53 Pricing.Note the following:You can't create a hosted
        zone for a top-level domain (TLD).Amazon Route 53 automatically creates a
        default SOA record and four NS records for the zone.For more information about
        SOA and NS records, see NS and SOA Records that Amazon Route 53 Creates for
        a Hosted Zone in the Amazon Route 53 Developer Guide.If your domain is registered
        with a registrar other than Amazon Route 53, you must update thename servers
        with your registrar to make Amazon Route 53 your DNS service. For more information,
        seeConfiguring Amazon Route 53 as your DNSService in the Amazon Route 53 Developer's
        Guide.After creating a zone, its initial status is PENDING. This means that
        itis not yet available on all DNS servers. The status of the zone changes
        to INSYNCwhen the NS and SOA records are available on all Amazon Route 53
        DNS servers. When trying to create a hosted zone using a reusable delegation
        set, specify anoptional DelegationSetId, and Amazon Route 53 would assign
        those 4 NS records for the zone, instead ofallotting a new one.
      operationId: createhostedzone
      x-api-path-slug: 20130401hostedzone-post
      parameters:
      - in: body
        name: CallerReference
        description: "A unique string that identifies the request and that allows
          failed\t\t\tCreateHostedZone requests to be retried without the risk of
          executing the\t\t\toperation twice"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateHostedZoneRequest
        description: Root level tag for the CreateHostedZoneRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Default
        description: None
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: DelegationSetId
        description: "If you want to associate a reusable delegation set with this
          hosted zone, the ID that\t\t\tAmazon Route 53 assigned to the reusable delegation
          set when you created it"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneConfig
        description: (Optional) A complex type that contains an optional comment about
          your hosted zone
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The name of the domain
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Parent
        description: CreatedHostedZoneRequest
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: VPC
        description: The VPC that you want your hosted zone to be associated with
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
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