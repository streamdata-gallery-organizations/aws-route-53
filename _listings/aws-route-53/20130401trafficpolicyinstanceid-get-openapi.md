---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API Get Traffic Policy Instance
  version: 1.0.0
  description: Gets information about a specified traffic policy instance.Send a GET
    request to the /Amazon Route 53 APIversion/trafficpolicyinstance resource.NoteAfter
    you submit a CreateTrafficPolicyInstance or anUpdateTrafficPolicyInstance request,
    there's a brief delay while Amazon Route 53creates the resource record sets that
    are specified in the traffic policy definition. Formore information, see the State
    response element.NoteIn the Amazon Route 53 console, traffic policy instances
    are known as policy records.
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
  /2013-04-01/delegationset:
    post:
      summary: Create Reusable Delegation Set
      description: Creates a delegation set (a group of four name servers) that can
        be reused by multiplehosted zones. If a hosted zoned ID is specified, CreateReusableDelegationSetmarks
        the delegation set associated with that zone as reusableSend a POST request
        to the /2013-04-01/delegationset resource. The request body must include a
        document with a CreateReusableDelegationSetRequest element.NoteA reusable
        delegation set can't be associated with a private hosted zone/For more information,
        including a procedure on how to create and configure a reusabledelegation
        set (also known as white label name servers), see Configuring White Label
        NameServers.
      operationId: createreusabledelegationset
      x-api-path-slug: 20130401delegationset-post
      parameters:
      - in: body
        name: CallerReference
        description: "A unique string that identifies the request, and that allows
          you to retry failed\t\t\t\tCreateReusableDelegationSet requests without
          the risk of executing the\t\t\toperation twice"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateReusableDelegationSetRequest
        description: Root level tag for the CreateReusableDelegationSetRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: "If you want to mark the delegation set for an existing hosted
          zone as reusable, the ID\t\t\tfor that hosted zone"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
  /2013-04-01/trafficpolicy:
    post:
      summary: Create Traffic Policy
      description: Creates a traffic policy, which you use to create multiple DNS
        resource record sets forone domain name (such as example.com) or one subdomain
        name (such aswww.example.com).Send a POST request to the /2013-04-01/trafficpolicy
        resource. The request body must include a documentwith a CreateTrafficPolicyRequest
        element. The response includes theCreateTrafficPolicyResponse element, which
        contains information about the newtraffic policy.
      operationId: createtrafficpolicy
      x-api-path-slug: 20130401trafficpolicy-post
      parameters:
      - in: body
        name: Comment
        description: (Optional) Any comments that you want to include about the traffic
          policy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateTrafficPolicyRequest
        description: Root level tag for the CreateTrafficPolicyRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Document
        description: The definition of this traffic policy in JSON format
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The name of the traffic policy
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
  /2013-04-01/trafficpolicyinstance:
    post:
      summary: Create Traffic Policy Instance
      description: Creates resource record sets in a specified hosted zone based on
        the settings in aspecified traffic policy version. In addition, CreateTrafficPolicyInstanceassociates
        the resource record sets with a specified domain name (such as example.com)
        orsubdomain name (such as www.example.com). Amazon Route 53 responds to DNS
        queries for the domain orsubdomain name by using the resource record sets
        that CreateTrafficPolicyInstancecreated.Send a POST request to the /2013-04-01/trafficpolicyinstance
        resource. The request body must include adocument with a CreateTrafficPolicyRequest
        element. The response returns theCreateTrafficPolicyInstanceResponse element,
        which contains information aboutthe traffic policy instance.
      operationId: createtrafficpolicyinstance
      x-api-path-slug: 20130401trafficpolicyinstance-post
      parameters:
      - in: body
        name: CreateTrafficPolicyInstanceRequest
        description: Root level tag for the CreateTrafficPolicyInstanceRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: "The ID of the hosted zone in which you want Amazon Route 53
          to create resource record sets by\t\t\tusing the configuration in a traffic
          policy"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The domain name (such as example
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TrafficPolicyId
        description: "The ID of the traffic policy that you want to use to create
          resource record sets in the\t\t\tspecified hosted zone"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TrafficPolicyVersion
        description: "The version of the traffic policy that you want to use to create
          resource record sets\t\t\tin the specified hosted zone"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: TTL
        description: "(Optional) The TTL that you want Amazon Route 53 to assign to
          all of the resource record sets\t\t\tthat it creates in the specified hosted
          zone"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
  /2013-04-01/trafficpolicy/Id:
    post:
      summary: Create Traffic Policy Version
      description: Creates a new version of an existing traffic policy. When you create
        a new version of atraffic policy, you specify the ID of the traffic policy
        that you want to update and aJSON-formatted document that describes the new
        version. You use traffic policies to createmultiple DNS resource record sets
        for one domain name (such as example.com) or one subdomainname (such as www.example.com).
        You can create a maximum of 1000 versions of a traffic policy.If you reach
        the limit and need to create another version, you'll need to start a new trafficpolicy.Send
        a POST request to the /2013-04-01/trafficpolicy/ resource. The request body
        includes a document witha CreateTrafficPolicyVersionRequest element. The response
        returns theCreateTrafficPolicyVersionResponse element, which contains information
        aboutthe new version of the traffic policy.
      operationId: createtrafficpolicyversion
      x-api-path-slug: 20130401trafficpolicyid-post
      parameters:
      - in: body
        name: Comment
        description: "The comment that you specified in the CreateTrafficPolicyVersion
          request,\t\t\tif any"
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateTrafficPolicyVersionRequest
        description: Root level tag for the CreateTrafficPolicyVersionRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Document
        description: The definition of this version of the traffic policy, in JSON
          format
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: The ID of the traffic policy for which you want to create a new
          version
        type: string
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
  /2013-04-01/hostedzone/Id/authorizevpcassociation:
    post:
      summary: Create V P C Association Authorization
      description: Authorizes the AWS account that created a specified VPC to submit
        an AssociateVPCWithHostedZone request to associate the VPC with a specified
        hosted zone that was created by a different account. To submit a CreateVPCAssociationAuthorization
        request, you must use the account that created the hosted zone. After you
        authorize the association, use the account that created the VPC to submit
        an AssociateVPCWithHostedZone request.NoteIf you want to associate multiple
        VPCs that you created by using one account with a hosted zone that you created
        by using a different account, you must submit one authorization request for
        each VPC.Send a POST request to the /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation
        resource. The request body must include a document with a CreateVPCAssociationAuthorizationRequest
        element. The response contains information about the authorization.
      operationId: createvpcassociationauthorization
      x-api-path-slug: 20130401hostedzoneidauthorizevpcassociation-post
      parameters:
      - in: body
        name: CreateVPCAssociationAuthorizationRequest
        description: Root level tag for the CreateVPCAssociationAuthorizationRequest
          parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: The ID of the private hosted zone that you want to authorize
          associating a VPC with
        type: string
      - in: body
        name: VPC
        description: "A complex type that contains the VPC ID and region for the VPC
          that you want to authorize associating \t\t\twith your hosted zone"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - VPC
  /2013-04-01/healthcheck/HealthCheckId:
    delete:
      summary: Delete Health Check
      description: Deletes a health check. Send a DELETE request to the/2013-04-01/healthcheck/health
        check ID            resource.ImportantAmazon Route 53 does not prevent you
        from deleting a health check even if the health check isassociated with one
        or more resource record sets. If you delete a health check and you don'tupdate
        the associated resource record sets, the future status of the health check
        can't bepredicted and may change. This will affect the routing of DNS queries
        for your DNS failoverconfiguration. For more information, see Replacing and
        Deleting Health Checks in the Amazon Route 53 Developer Guide.
      operationId: deletehealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-delete
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID of the health check that you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
    get:
      summary: Get Health Check
      description: Gets information about a specified health check. Send a GET request
        to the/2013-04-01/healthcheck/health check ID             resource. Formore
        information about using the console to perform this operation, see Amazon
        Route 53 Health Checks and DNS Failover in theAmazon Route 53 Developer Guide.
      operationId: gethealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-get
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
      - Checks
      - Health
  /2013-04-01/hostedzone/Id:
    delete:
      summary: Delete Hosted Zone
      description: Deletes a hosted zone. Send a DELETE request to the /Amazon Route
        53API version/hostedzone/hosted zone ID             resource.ImportantDelete
        a hosted zone only if there are no resource record sets other than the defaultSOA
        record and NS resource record sets. If the hosted zone contains other resource
        recordsets, delete them before deleting the hosted zone. If you try to delete
        a hosted zone thatcontains other resource record sets, Amazon Route 53 denies
        your request with aHostedZoneNotEmpty error. For information about deleting
        records from yourhosted zone, see ChangeResourceRecordSets.
      operationId: deletehostedzone
      x-api-path-slug: 20130401hostedzoneid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
    get:
      summary: Get Hosted Zone
      description: Retrieves the delegation set for a hosted zone, including the four
        name serversassigned to the hosted zone. Send a GET request to the /Amazon
        Route 53 APIversion/hostedzone/hosted zone ID             resource.
      operationId: gethostedzone
      x-api-path-slug: 20130401hostedzoneid-get
      parameters:
      - in: path
        name: Id
        description: "The ID of the hosted zone for which you want to get a list of
          the name servers in the\t\t\tdelegation set"
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
  /2013-04-01/delegationset/Id:
    delete:
      summary: Delete Reusable Delegation Set
      description: Deletes a reusable delegation set. Send a DELETE request to the/2013-04-01/delegationset/delegation
        set ID            resource.Important You can delete a reusable delegation
        set only if there are no associated hostedzones.To verify that the reusable
        delegation set is not associated with any hosted zones, runthe GetReusableDelegationSet
        action and specify the ID of the reusabledelegation set that you want to delete.
      operationId: deletereusabledelegationset
      x-api-path-slug: 20130401delegationsetid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the reusable delegation set you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
    get:
      summary: Get Reusable Delegation Set
      description: Retrieves the reusable delegation set. Send a GET request to the/2013-04-01/delegationset/delegation
        set ID            resource.
      operationId: getreusabledelegationset
      x-api-path-slug: 20130401delegationsetid-get
      parameters:
      - in: path
        name: Id
        description: "The ID of the reusable delegation set for which you want to
          get a list of the name\t\t\tserver"
        type: string
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
  /2013-04-01/trafficpolicy/Id/Version:
    delete:
      summary: Delete Traffic Policy
      description: Deletes a traffic policy.Send a DELETE request to the /Amazon Route
        53 APIversion/trafficpolicy resource.
      operationId: deletetrafficpolicy
      x-api-path-slug: 20130401trafficpolicyidversion-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the traffic policy that you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
    get:
      summary: Get Traffic Policy
      description: Gets information about a specific traffic policy version.Send a
        GET request to the /Amazon Route 53 APIversion/trafficpolicy resource.
      operationId: gettrafficpolicy
      x-api-path-slug: 20130401trafficpolicyidversion-get
      parameters:
      - in: path
        name: Id
        description: The ID of the traffic policy that you want to get information
          about
        type: string
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
  /2013-04-01/trafficpolicyinstance/Id:
    delete:
      summary: Delete Traffic Policy Instance
      description: Deletes a traffic policy instance and all of the resource record
        sets that Amazon Route 53created when you created the instance.Send a DELETE
        request to the /Amazon Route 53 APIversion/trafficpolicy/traffic policy instance
        ID            resource.NoteIn the Amazon Route 53 console, traffic policy
        instances are known as policy records.
      operationId: deletetrafficpolicyinstance
      x-api-path-slug: 20130401trafficpolicyinstanceid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the traffic policy instance that you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
    get:
      summary: Get Traffic Policy Instance
      description: Gets information about a specified traffic policy instance.Send
        a GET request to the /Amazon Route 53 APIversion/trafficpolicyinstance resource.NoteAfter
        you submit a CreateTrafficPolicyInstance or anUpdateTrafficPolicyInstance
        request, there's a brief delay while Amazon Route 53creates the resource record
        sets that are specified in the traffic policy definition. Formore information,
        see the State response element.NoteIn the Amazon Route 53 console, traffic
        policy instances are known as policy records.
      operationId: gettrafficpolicyinstance
      x-api-path-slug: 20130401trafficpolicyinstanceid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the traffic policy instance that you want to get information
          about
        type: string
      responses:
        200:
          description: OK
      tags:
      - Traffic Policies
  /2013-04-01/hostedzone/Id/deauthorizevpcassociation:
    post:
      summary: Delete V P C Association Authorization
      description: Removes authorization to submit an AssociateVPCWithHostedZone request
        to associate a specified VPC with a hosted zone that was created by a different
        account. You must use the account that created the hosted zone to submit a
        DeleteVPCAssociationAuthorization request.ImportantSending this request only
        prevents the AWS account that created the VPC from associating the VPC with
        the Amazon Route 53 hosted zone in the future. If the VPC is already associated
        with the hosted zone, DeleteVPCAssociationAuthorization won't disassociate
        the VPC from the hosted zone. If you want to delete an existing association,
        use DisassociateVPCFromHostedZone.Send a DELETE request to the /2013-04-01/hostedzone/hosted
        zone ID/deauthorizevpcassociation resource. The request body must include
        a document with a DeleteVPCAssociationAuthorizationRequest element.
      operationId: deletevpcassociationauthorization
      x-api-path-slug: 20130401hostedzoneiddeauthorizevpcassociation-post
      parameters:
      - in: body
        name: DeleteVPCAssociationAuthorizationRequest
        description: Root level tag for the DeleteVPCAssociationAuthorizationRequest
          parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: "When removing authorization to associate a VPC that was created
          by one AWS account with a hosted zone \t\t\tthat was created with a different
          AWS account, the ID of the hosted zone"
        type: string
      - in: body
        name: VPC
        description: "When removing authorization to associate a VPC that was created
          by one AWS account with a hosted zone \t\t\tthat was created with a different
          AWS account, a complex type that includes the ID and region of the VPC"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - VPC
  /2013-04-01/hostedzone/Id/disassociatevpc:
    post:
      summary: Disassociate V P C From Hosted Zone
      description: Disassociates a VPC from a Amazon Route 53 private hosted zone.
        NoteYou can't disassociate the last VPC from a private hosted zone.Send a
        POST request to the /2013-04-01/hostedzone/hosted zone ID/disassociatevpcresource.
        The request body must include a document with a DisassociateVPCFromHostedZoneRequest
        element. The response includes a DisassociateVPCFromHostedZoneResponse element.ImportantYou
        can't disassociate a VPC from a private hosted zone when only one VPC is associated
        with the hosted zone. You also can't convert a private hosted zone into a
        public hosted zone.
      operationId: disassociatevpcfromhostedzone
      x-api-path-slug: 20130401hostedzoneiddisassociatevpc-post
      parameters:
      - in: body
        name: Comment
        description: 'Optional: A comment about the disassociation request'
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: DisassociateVPCFromHostedZoneRequest
        description: Root level tag for the DisassociateVPCFromHostedZoneRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: Id
        description: The ID of the private hosted zone that you want to disassociate
          a VPC from
        type: string
      - in: body
        name: VPC
        description: "A complex type that contains information about the VPC that
          youre disassociating\t\t\tfrom the specified hosted zone"
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - VPC
  /2013-04-01/change/Id:
    get:
      summary: Get Change
      description: 'Returns the current status of a change batch request. The status
        is one of thefollowing values:                  PENDING indicates that the
        changes in this request have not replicatedto all Amazon Route 53 DNS servers.
        This is the initial status of all change batchrequests.                  INSYNC
        indicates that the changes have replicated to all Amazon Route 53 DNSservers.'
      operationId: getchange
      x-api-path-slug: 20130401changeid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the change batch request
        type: string
      responses:
        200:
          description: OK
      tags:
      - Changes
  /2013-04-01/checkeripranges:
    get:
      summary: Get Checker Ip Ranges
      description: GetCheckerIpRanges still works, but we recommend that you download
        ip-ranges.json, which includes IP address ranges for all AWS services. For
        more information, see IP Address Ranges of Amazon Route 53 Servers in the
        Amazon Route 53 Developer Guide.
      operationId: getcheckeripranges
      x-api-path-slug: 20130401checkeripranges-get
      responses:
        200:
          description: OK
      tags:
      - IP Ranges
  /2013-04-01/geolocation?continentcode=ContinentCode&amp;countrycode=CountryCode&amp;subdivisioncode=SubdivisionCode:
    get:
      summary: Get Geo Location
      description: 'Retrieves a single geo location. Send a GET request to the/2013-04-01/geolocation
        resource with one of these options: continentcode |countrycode | countrycode
        and subdivisioncode.'
      operationId: getgeolocation
      x-api-path-slug: 20130401geolocationcontinentcodecontinentcodeampcountrycodecountrycodeampsubdivisioncodesubdivisioncode-get
      parameters:
      - in: path
        name: continentcode
        description: 'Amazon Route 53 supports the following continent codes:                        AF:
          Africa                        AN: Antarctica                        AS:
          Asia                        EU: Europe                        OC: Oceania                        NA:
          North America                        SA: South AmericaLength Constraints:
          Fixed length of 2'
        type: string
      responses:
        200:
          description: OK
      tags:
      - Locations
  /2013-04-01/healthcheckcount:
    get:
      summary: Get Health Check Count
      description: To retrieve a count of all your health checks, send a GET request
        to the/2013-04-01/healthcheckcount resource.
      operationId: gethealthcheckcount
      x-api-path-slug: 20130401healthcheckcount-get
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId/lastfailurereason:
    get:
      summary: Get Health Check Last Failure Reason
      description: If you want to learn why a health check is currently failing or
        why it failed mostrecently (if at all), you can get the failure reason for
        the most recent failure. Send aGET request to the /Amazon Route 53 APIversion/healthcheck/health
        checkID/lastfailurereason resource.
      operationId: gethealthchecklastfailurereason
      x-api-path-slug: 20130401healthcheckhealthcheckidlastfailurereason-get
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
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId/status:
    get:
      summary: Get Health Check Status
      description: Gets status of a specified health check. Send a GET request to
        the/2013-04-01/healthcheck/health check ID/status resource.You can use this
        call to get a health check's current status.
      operationId: gethealthcheckstatus
      x-api-path-slug: 20130401healthcheckhealthcheckidstatus-get
      parameters:
      - in: path
        name: HealthCheckId
        description: "If you want Amazon Route 53 to return this resource record set
          in response to a DNS query only\t\t\twhen a health check is passing, include
          the HealthCheckId element and specify the\t\t\tID of the applicable health
          check"
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/hostedzonecount:
    get:
      summary: Get Hosted Zone Count
      description: Retrieves a count of all your hosted zones. Send a GET request
        to the/2013-04-01/hostedzonecount resource.
      operationId: gethostedzonecount
      x-api-path-slug: 20130401hostedzonecount-get
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