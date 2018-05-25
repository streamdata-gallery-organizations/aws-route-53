---
name: AWS Route 53
x-slug: aws-route-53
description: Amazon Route 53 is a highly available and scalable cloud Domain Name
  System (DNS) web service. It is designed to give developers and businesses an extremely
  reliable and cost effective way to route end users to Internet applications by translating
  names like www.example.com into the numeric IP addresses like 192.0.2.1 that computers
  use to connect to each other. Amazon Route 53 is fully compliant with IPv6 as well.Amazon
  Route 53 effectively connects user requests to infrastructure running in AWS &ndash;
  such as Amazon EC2 instances, Elastic Load Balancing load balancers, or Amazon S3
  buckets &ndash; and can also be used to route users to infrastructure outside of
  AWS. You can use Amazon Route 53 to configure DNS health checks to route traffic
  to healthy endpoints or to independently monitor the health of your application
  and its endpoints. Amazon Route 53 Traffic Flow makes it easy for you to manage
  traffic globally through a variety of routing types, including Latency Based Routing,
  Geo DNS, and Weighted Round Robin&mdash;all of which can be combined with DNS Failover
  in order to enable a variety of low-latency, fault-tolerant architectures. Using
  Amazon Route 53 Traffic Flow&rsquo;s simple visual editor, you can easily manage
  how your end-users are routed to your application&rsquo;s endpoints&mdash;whether
  in a single AWS region or distributed around the globe. Amazon Route 53 also offers
  Domain Name Registration &ndash; you can purchase and manage domain names such as
  example.com and Amazon Route 53 will automatically configure DNS settings for your
  domains.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
x-kinRank: "8"
x-alexaRank: ""
tags: AWS Route 53
created: "2018-05-24"
modified: "2018-05-24"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/apis.md
specificationVersion: "0.14"
apis:
- name: AWS Route 53 API Associate V P C With Hosted Zone
  x-api-slug: aws-route-53-api
  description: Associates an Amazon VPC with a private hosted zone. ImportantTo perform
    the association, the VPC and the private hosted zone must already exist. You can't
    convert a public hosted zone into a private hosted zone.Send a POST request to
    the /2013-04-01/hostedzone/hosted zone ID/associatevpc resource. The request body
    must include a document with an AssociateVPCWithHostedZoneRequest element. The
    response contains a ChangeInfo data type that you can use to track the progress
    of the request. NoteIf you want to associate a VPC that was created by using one
    AWS account with a private hosted zone that was created by using a different account,
    the AWS account that created the private hosted zone must first submit a CreateVPCAssociationAuthorization
    request. Then the account that created the VPC must submit an AssociateVPCWithHostedZone
    request.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/associatevpc
  tags: VPC
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneidassociatevpc-post-openapi.md
- name: AWS Route 53 API Change Resource Record Sets
  x-api-slug: aws-route-53-api
  description: 'Create, change, update, or delete authoritative DNS information on
    all Amazon Route 53 servers.Send a POST request to:             /2013-04-01/hostedzone/Amazon
    Route 53 hosted ZoneID/rrset resource. The request body must include a document
    with aChangeResourceRecordSetsRequest element. The request body contains a list
    ofchange items, known as a change batch. Change batches are considered transactional
    changes.When using the Amazon Route 53 API to change resource record sets, Amazon
    Route 53 either makes all or none of thechanges in a change batch request. This
    ensures that Amazon Route 53 never partially implements theintended changes to
    the resource record sets in a hosted zone. For example, a change batch request
    that deletes the CNAME record forwww.example.com and creates an alias resource
    record set for www.example.com. Amazon Route 53 deletesthe first resource record
    set and creates the second resource record set in a singleoperation. If either
    the DELETE or the CREATE action fails, thenboth changes (plus any other changes
    in the batch) fail, and the original CNAMErecord continues to exist.ImportantDue
    to the nature of transactional changes, you can''t delete the same resourcerecord
    set more than once in a single change batch. If you attempt to delete the same
    changebatch more than once, Amazon Route 53 returns an InvalidChangeBatch error.NoteTo
    create resource record sets for complex routing configurations, use either thetraffic
    flow visual editor in the Amazon Route 53 console or the API actions for traffic
    policies andtraffic policy instances. Save the configuration as a traffic policy,
    then associate thetraffic policy with one or more domain names (such as example.com)
    or subdomain names (suchas www.example.com), in the same hosted zone or in multiple
    hosted zones. You can roll backthe updates if the new configuration isn''t performing
    as expected. For more information, seeUsing Traffic Flow to Route DNSTraffic in
    the Amazon Route 53 Developer Guide.Use ChangeResourceRecordsSetsRequest to perform
    the following actions:                  CREATE: Creates a resource record set
    that has the specified values.                  DELETE: Deletes an existing resource
    record set that has the specified values.                  UPSERT: If a resource
    record set does not already exist, AWS createsit. If a resource set does exist,
    Amazon Route 53 updates it with the values in the request. The values that you
    need to include in the request depend on the type of resource record set that
    you''re creating, deleting, or updating:            Basic resource record sets
    (excluding alias, failover, geolocation, latency, and weighted resource record
    sets)                           Name                                 Type                                 TTL                           Failover,
    geolocation, latency, or weighted resource record sets (excluding alias resource
    record sets)                           Name                                 Type                                 TTL                                 SetIdentifier                           Alias
    resource record sets (including failover alias, geolocation alias, latency alias,
    and weighted alias resource record sets)                           Name                                 Type                                 AliasTarget
    (includes DNSName, EvaluateTargetHealth, and HostedZoneId)                  SetIdentifier
    (for failover, geolocation, latency, and weighted resource record sets)When you
    submit a ChangeResourceRecordSets request, Amazon Route 53 propagates your changes
    to all of the Amazon Route 53 authoritative DNS servers. While your changes are
    propagating, GetChange returns a status of PENDING. When propagation is complete,
    GetChange returns a status of INSYNC. Changes generally propagate to all Amazon
    Route 53 name servers in a few minutes. In rare circumstances, propagation can
    take up to 30 minutes. For more information, see GetChange       For information
    about the limits on a ChangeResourceRecordSets request, see Limits in the Amazon
    Route 53 Developer Guide.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/rrset/
  tags: Changes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneidrrset-post-openapi.md
- name: AWS Route 53 API Change Tags For Resource
  x-api-slug: aws-route-53-api
  description: Adds, edits, or deletes tags for a health check or a hosted zone.For
    information about using tags for cost allocation, see Using Cost Allocation Tags
    in the AWS Billing and Cost Management User Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/tags/ResourceType/ResourceId
  tags: Changes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401tagsresourcetyperesourceid-post-openapi.md
- name: AWS Route 53 API Create Health Check
  x-api-slug: aws-route-53-api
  description: Creates a new health check.To create a new health check, send a POST
    request to the/2013-04-01/healthcheck resource. The request body must include
    a documentwith a CreateHealthCheckRequest element. The response returns theCreateHealthCheckResponse
    element, containing the health check ID specifiedwhen adding health check to a
    resource record set. For information about adding health checksto resource record
    sets, see ResourceRecordSet:HealthCheckId in ChangeResourceRecordSets. If you
    are registering EC2 instances with an Elastic Load Balancing (ELB) loadbalancer,
    do not create Amazon Route 53 health checks for the EC2 instances. When you register
    anEC2 instance with a load balancer, you configure settings for an ELB health
    check, whichperforms a similar function to an Amazon Route 53 health check.You
    can associate health checks with failover resource record sets in a private hostedzone.
    Note the following:Amazon Route 53 health checkers are outside the VPC. To check
    the health of an endpointwithin a VPC by IP address, you must assign a public
    IP address to the instance in theVPC.You can configure a health checker to check
    the health of an external resource thatthe instance relies on, such as a database
    server.You can create a CloudWatch metric, associate an alarm with the metric,
    and then create ahealth check that is based on the state of the alarm. For example,
    you might create a CloudWatchmetric that checks the status of the Amazon EC2 StatusCheckFailed
    metric, add analarm to the metric, and then create a health check that is based
    on the state of thealarm. For information about creating CloudWatch metrics and
    alarms by using the CloudWatch console,see the Amazon CloudWatch User Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheck-post-openapi.md
- name: AWS Route 53 API Create Hosted Zone
  x-api-slug: aws-route-53-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzone-post-openapi.md
- name: AWS Route 53 API Create Reusable Delegation Set
  x-api-slug: aws-route-53-api
  description: Creates a delegation set (a group of four name servers) that can be
    reused by multiplehosted zones. If a hosted zoned ID is specified, CreateReusableDelegationSetmarks
    the delegation set associated with that zone as reusableSend a POST request to
    the /2013-04-01/delegationset resource. The request body must include a document
    with a CreateReusableDelegationSetRequest element.NoteA reusable delegation set
    can't be associated with a private hosted zone/For more information, including
    a procedure on how to create and configure a reusabledelegation set (also known
    as white label name servers), see Configuring White Label NameServers.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/delegationset
  tags: Reusable Delegation Sets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401delegationset-post-openapi.md
- name: AWS Route 53 API Create Traffic Policy
  x-api-slug: aws-route-53-api
  description: Creates a traffic policy, which you use to create multiple DNS resource
    record sets forone domain name (such as example.com) or one subdomain name (such
    aswww.example.com).Send a POST request to the /2013-04-01/trafficpolicy resource.
    The request body must include a documentwith a CreateTrafficPolicyRequest element.
    The response includes theCreateTrafficPolicyResponse element, which contains information
    about the newtraffic policy.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicy
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicy-post-openapi.md
- name: AWS Route 53 API Create Traffic Policy Instance
  x-api-slug: aws-route-53-api
  description: Creates resource record sets in a specified hosted zone based on the
    settings in aspecified traffic policy version. In addition, CreateTrafficPolicyInstanceassociates
    the resource record sets with a specified domain name (such as example.com) orsubdomain
    name (such as www.example.com). Amazon Route 53 responds to DNS queries for the
    domain orsubdomain name by using the resource record sets that CreateTrafficPolicyInstancecreated.Send
    a POST request to the /2013-04-01/trafficpolicyinstance resource. The request
    body must include adocument with a CreateTrafficPolicyRequest element. The response
    returns theCreateTrafficPolicyInstanceResponse element, which contains information
    aboutthe traffic policy instance.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstance
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstance-post-openapi.md
- name: AWS Route 53 API Create Traffic Policy Version
  x-api-slug: aws-route-53-api
  description: Creates a new version of an existing traffic policy. When you create
    a new version of atraffic policy, you specify the ID of the traffic policy that
    you want to update and aJSON-formatted document that describes the new version.
    You use traffic policies to createmultiple DNS resource record sets for one domain
    name (such as example.com) or one subdomainname (such as www.example.com). You
    can create a maximum of 1000 versions of a traffic policy.If you reach the limit
    and need to create another version, you'll need to start a new trafficpolicy.Send
    a POST request to the /2013-04-01/trafficpolicy/ resource. The request body includes
    a document witha CreateTrafficPolicyVersionRequest element. The response returns
    theCreateTrafficPolicyVersionResponse element, which contains information aboutthe
    new version of the traffic policy.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicy/Id
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyid-post-openapi.md
- name: AWS Route 53 API Create V P C Association Authorization
  x-api-slug: aws-route-53-api
  description: Authorizes the AWS account that created a specified VPC to submit an
    AssociateVPCWithHostedZone request to associate the VPC with a specified hosted
    zone that was created by a different account. To submit a CreateVPCAssociationAuthorization
    request, you must use the account that created the hosted zone. After you authorize
    the association, use the account that created the VPC to submit an AssociateVPCWithHostedZone
    request.NoteIf you want to associate multiple VPCs that you created by using one
    account with a hosted zone that you created by using a different account, you
    must submit one authorization request for each VPC.Send a POST request to the
    /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation resource. The request
    body must include a document with a CreateVPCAssociationAuthorizationRequest element.
    The response contains information about the authorization.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/authorizevpcassociation
  tags: VPC
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneidauthorizevpcassociation-post-openapi.md
- name: AWS Route 53 API Delete Health Check
  x-api-slug: aws-route-53-api
  description: Deletes a health check. Send a DELETE request to the/2013-04-01/healthcheck/health
    check ID            resource.ImportantAmazon Route 53 does not prevent you from
    deleting a health check even if the health check isassociated with one or more
    resource record sets. If you delete a health check and you don'tupdate the associated
    resource record sets, the future status of the health check can't bepredicted
    and may change. This will affect the routing of DNS queries for your DNS failoverconfiguration.
    For more information, see Replacing and Deleting Health Checks in the Amazon Route
    53 Developer Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck/HealthCheckId
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckhealthcheckid-delete-openapi.md
- name: AWS Route 53 API Delete Hosted Zone
  x-api-slug: aws-route-53-api
  description: Deletes a hosted zone. Send a DELETE request to the /Amazon Route 53API
    version/hostedzone/hosted zone ID             resource.ImportantDelete a hosted
    zone only if there are no resource record sets other than the defaultSOA record
    and NS resource record sets. If the hosted zone contains other resource recordsets,
    delete them before deleting the hosted zone. If you try to delete a hosted zone
    thatcontains other resource record sets, Amazon Route 53 denies your request with
    aHostedZoneNotEmpty error. For information about deleting records from yourhosted
    zone, see ChangeResourceRecordSets.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneid-delete-openapi.md
- name: AWS Route 53 API Delete Reusable Delegation Set
  x-api-slug: aws-route-53-api
  description: Deletes a reusable delegation set. Send a DELETE request to the/2013-04-01/delegationset/delegation
    set ID            resource.Important You can delete a reusable delegation set
    only if there are no associated hostedzones.To verify that the reusable delegation
    set is not associated with any hosted zones, runthe GetReusableDelegationSet action
    and specify the ID of the reusabledelegation set that you want to delete.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/delegationset/Id
  tags: Reusable Delegation Sets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401delegationsetid-delete-openapi.md
- name: AWS Route 53 API Delete Traffic Policy
  x-api-slug: aws-route-53-api
  description: Deletes a traffic policy.Send a DELETE request to the /Amazon Route
    53 APIversion/trafficpolicy resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicy/Id/Version
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyidversion-delete-openapi.md
- name: AWS Route 53 API Delete Traffic Policy Instance
  x-api-slug: aws-route-53-api
  description: Deletes a traffic policy instance and all of the resource record sets
    that Amazon Route 53created when you created the instance.Send a DELETE request
    to the /Amazon Route 53 APIversion/trafficpolicy/traffic policy instance ID            resource.NoteIn
    the Amazon Route 53 console, traffic policy instances are known as policy records.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstance/Id
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstanceid-delete-openapi.md
- name: AWS Route 53 API Delete V P C Association Authorization
  x-api-slug: aws-route-53-api
  description: Removes authorization to submit an AssociateVPCWithHostedZone request
    to associate a specified VPC with a hosted zone that was created by a different
    account. You must use the account that created the hosted zone to submit a DeleteVPCAssociationAuthorization
    request.ImportantSending this request only prevents the AWS account that created
    the VPC from associating the VPC with the Amazon Route 53 hosted zone in the future.
    If the VPC is already associated with the hosted zone, DeleteVPCAssociationAuthorization
    won't disassociate the VPC from the hosted zone. If you want to delete an existing
    association, use DisassociateVPCFromHostedZone.Send a DELETE request to the /2013-04-01/hostedzone/hosted
    zone ID/deauthorizevpcassociation resource. The request body must include a document
    with a DeleteVPCAssociationAuthorizationRequest element.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/deauthorizevpcassociation
  tags: VPC
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneiddeauthorizevpcassociation-post-openapi.md
- name: AWS Route 53 API Disassociate V P C From Hosted Zone
  x-api-slug: aws-route-53-api
  description: Disassociates a VPC from a Amazon Route 53 private hosted zone. NoteYou
    can't disassociate the last VPC from a private hosted zone.Send a POST request
    to the /2013-04-01/hostedzone/hosted zone ID/disassociatevpcresource. The request
    body must include a document with a DisassociateVPCFromHostedZoneRequest element.
    The response includes a DisassociateVPCFromHostedZoneResponse element.ImportantYou
    can't disassociate a VPC from a private hosted zone when only one VPC is associated
    with the hosted zone. You also can't convert a private hosted zone into a public
    hosted zone.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/disassociatevpc
  tags: VPC
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneiddisassociatevpc-post-openapi.md
- name: AWS Route 53 API Get Change
  x-api-slug: aws-route-53-api
  description: 'Returns the current status of a change batch request. The status is
    one of thefollowing values:                  PENDING indicates that the changes
    in this request have not replicatedto all Amazon Route 53 DNS servers. This is
    the initial status of all change batchrequests.                  INSYNC indicates
    that the changes have replicated to all Amazon Route 53 DNSservers.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/change/Id
  tags: Changes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401changeid-get-openapi.md
- name: AWS Route 53 API Get Checker Ip Ranges
  x-api-slug: aws-route-53-api
  description: GetCheckerIpRanges still works, but we recommend that you download
    ip-ranges.json, which includes IP address ranges for all AWS services. For more
    information, see IP Address Ranges of Amazon Route 53 Servers in the Amazon Route
    53 Developer Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/checkeripranges
  tags: IP Ranges
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401checkeripranges-get-openapi.md
- name: AWS Route 53 API Get Geo Location
  x-api-slug: aws-route-53-api
  description: 'Retrieves a single geo location. Send a GET request to the/2013-04-01/geolocation
    resource with one of these options: continentcode |countrycode | countrycode and
    subdivisioncode.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/geolocation?continentcode=ContinentCode&amp;countrycode=CountryCode&amp;subdivisioncode=SubdivisionCode
  tags: Locations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401geolocationcontinentcodecontinentcodeampcountrycodecountrycodeampsubdivisioncodesubdivisioncode-get-openapi.md
- name: AWS Route 53 API Get Health Check
  x-api-slug: aws-route-53-api
  description: Gets information about a specified health check. Send a GET request
    to the/2013-04-01/healthcheck/health check ID             resource. Formore information
    about using the console to perform this operation, see Amazon Route 53 Health
    Checks and DNS Failover in theAmazon Route 53 Developer Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck/HealthCheckId
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckhealthcheckid-get-openapi.md
- name: AWS Route 53 API Get Health Check Count
  x-api-slug: aws-route-53-api
  description: To retrieve a count of all your health checks, send a GET request to
    the/2013-04-01/healthcheckcount resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheckcount
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckcount-get-openapi.md
- name: AWS Route 53 API Get Health Check Last Failure Reason
  x-api-slug: aws-route-53-api
  description: If you want to learn why a health check is currently failing or why
    it failed mostrecently (if at all), you can get the failure reason for the most
    recent failure. Send aGET request to the /Amazon Route 53 APIversion/healthcheck/health
    checkID/lastfailurereason resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck/HealthCheckId/lastfailurereason
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckhealthcheckidlastfailurereason-get-openapi.md
- name: AWS Route 53 API Get Health Check Status
  x-api-slug: aws-route-53-api
  description: Gets status of a specified health check. Send a GET request to the/2013-04-01/healthcheck/health
    check ID/status resource.You can use this call to get a health check's current
    status.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck/HealthCheckId/status
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckhealthcheckidstatus-get-openapi.md
- name: AWS Route 53 API Get Hosted Zone
  x-api-slug: aws-route-53-api
  description: Retrieves the delegation set for a hosted zone, including the four
    name serversassigned to the hosted zone. Send a GET request to the /Amazon Route
    53 APIversion/hostedzone/hosted zone ID             resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneid-get-openapi.md
- name: AWS Route 53 API Get Hosted Zone Count
  x-api-slug: aws-route-53-api
  description: Retrieves a count of all your hosted zones. Send a GET request to the/2013-04-01/hostedzonecount
    resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzonecount
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzonecount-get-openapi.md
- name: AWS Route 53 API Get Reusable Delegation Set
  x-api-slug: aws-route-53-api
  description: Retrieves the reusable delegation set. Send a GET request to the/2013-04-01/delegationset/delegation
    set ID            resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/delegationset/Id
  tags: Reusable Delegation Sets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401delegationsetid-get-openapi.md
- name: AWS Route 53 API Get Traffic Policy
  x-api-slug: aws-route-53-api
  description: Gets information about a specific traffic policy version.Send a GET
    request to the /Amazon Route 53 APIversion/trafficpolicy resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicy/Id/Version
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyidversion-get-openapi.md
- name: AWS Route 53 API Get Traffic Policy Instance
  x-api-slug: aws-route-53-api
  description: Gets information about a specified traffic policy instance.Send a GET
    request to the /Amazon Route 53 APIversion/trafficpolicyinstance resource.NoteAfter
    you submit a CreateTrafficPolicyInstance or anUpdateTrafficPolicyInstance request,
    there's a brief delay while Amazon Route 53creates the resource record sets that
    are specified in the traffic policy definition. Formore information, see the State
    response element.NoteIn the Amazon Route 53 console, traffic policy instances
    are known as policy records.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstance/Id
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstanceid-get-openapi.md
- name: AWS Route 53 API Get Traffic Policy Instance Count
  x-api-slug: aws-route-53-api
  description: Gets the number of traffic policy instances that are associated with
    the current AWSaccount.To get the number of traffic policy instances, send a GET
    request to the/2013-04-01/trafficpolicyinstancecount resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstancecount
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstancecount-get-openapi.md
- name: AWS Route 53 API List Geo Locations
  x-api-slug: aws-route-53-api
  description: Retrieves a list of supported geo locations. Send a GET request to
    the/2013-04-01/geolocations resource. The response to this request includes aGeoLocationDetailsList
    element for each location that Amazon Route 53 supports.Countries are listed first,
    and continents are listed last. If Amazon Route 53 supportssubdivisions for a
    country (for example, states or provinces), the subdivisions for thatcountry are
    listed in alphabetical order immediately after the corresponding country.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/geolocations&amp;maxitems=MaxItems?startcontinentcode=StartContinentCode&amp;startcountrycode=StartCountryCode&amp;startsubdivisioncode=StartSubdivisionCode
  tags: Locations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401geolocationsampmaxitemsmaxitemsstartcontinentcodestartcontinentcodeampstartcountrycodestartcountrycodeampstartsubdivisioncodestartsubdivisioncode-get-openapi.md
- name: AWS Route 53 API List Health Checks
  x-api-slug: aws-route-53-api
  description: Retrieve a list of your health checks. Send a GET request to the/2013-04-01/healthcheck
    resource. The response to this request includes aHealthChecks element with zero
    or more HealthCheck child elements.By default, the list of health checks is displayed
    on a single page. You can control thelength of the page that is displayed by using
    the MaxItems parameter. You can usethe Marker parameter to control the health
    check that the list beginswith.For information about listing health checks using
    the Amazon Route 53 console, see Amazon Route 53 Health Checks and DNS Failover.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck?marker=Marker&amp;maxitems=MaxItems
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckmarkermarkerampmaxitemsmaxitems-get-openapi.md
- name: AWS Route 53 API List Hosted Zones
  x-api-slug: aws-route-53-api
  description: 'To retrieve a list of your public and private hosted zones, send a
    GETrequest to the /2013-04-01/hostedzone resource. The response to this requestincludes
    a HostedZones child element for each hosted zone created by the currentAWS account.Amazon
    Route 53 returns a maximum of 100 items in each response. If you have a lot of
    hostedzones, you can use the maxitems parameter to list them in groups of up to
    100.The response includes four values that help navigate from one group of maxitemshosted
    zones to the next:                  MaxItems is the value specified for the maxitems
    parameterin the request that produced the current response.If the value of IsTruncated
    in the response is true, there are morehosted zones associated with the current
    AWS account.                   NextMarker is the hosted zone ID of the next hosted
    zone that isassociated with the current AWS account. If you want to list more
    hosted zones, makeanother call to ListHostedZones, and specify the value of theNextMarker
    element in the marker parameter. If IsTruncated is false, the NextMarker element
    isomitted from the response.If you''re making the second or subsequent call to
    ListHostedZones, theMarker element matches the value that you specified in themarker
    parameter in the previous request.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone&amp;delegationsetid=DelegationSetId?marker=Marker&amp;maxitems=MaxItems
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneampdelegationsetiddelegationsetidmarkermarkerampmaxitemsmaxitems-get-openapi.md
- name: AWS Route 53 API List Hosted Zones By Name
  x-api-slug: aws-route-53-api
  description: 'Retrieves a list of your hosted zones in lexicographic order. Send
    a GETrequest to the /2013-04-01/hostedzonesbyname resource. The response includes
    aHostedZones child element for each hosted zone created by the current AWSaccount.             ListHostedZonesByName
    sorts hosted zones by name with the labels reversed.For example:                  com.example.www.               Note
    the trailing dot, which can change the sort order in some circumstances.If the
    domain name includes escape characters or Punycode,ListHostedZonesByName alphabetizes
    the domain name using the escaped orPunycoded value, which is the format that
    Amazon Route 53 saves in its database. For example, to createa hosted zone for
    example.com, specify ex\344mple.com for the domain name.ListHostedZonesByName
    alphabetizes it as:                  com.ex\344mple.               The labels
    are reversed and alphabetized using the escaped value. For more informationabout
    valid domain name formats, including internationalized domain names, see DNS Domain
    Name Format in theAmazon Route 53 Developer Guide.Amazon Route 53 returns up to
    100 items in each response. If you have a lot of hosted zones, usethe MaxItems
    parameter to list them in groups of up to 100. The response includesvalues that
    help navigate from one group of MaxItems hosted zones to thenext:The DNSName and
    HostedZoneId elements in the responsecontain the values, if any, specified for
    the dnsname andhostedzoneid parameters in the request that produced the currentresponse.The
    MaxItems element in the response contains the value, if any, thatyou specified
    for the maxitems parameter in the request that produced thecurrent response.If
    the value of IsTruncated in the response is true, there are morehosted zones associated
    with the current AWS account. If IsTruncated is false, this response includes
    the last hosted zonethat is associated with the current account. The NextDNSName
    element andNextHostedZoneId elements are omitted from the response.The NextDNSName
    and NextHostedZoneId elements in theresponse contain the domain name and the hosted
    zone ID of the next hosted zone that isassociated with the current AWS account.
    If you want to list more hosted zones, makeanother call to ListHostedZonesByName,
    and specify the value ofNextDNSName and NextHostedZoneId in the dnsnameand hostedzoneid
    parameters, respectively.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzonesbyname?dnsname=DNSName&amp;hostedzoneid=HostedZoneId&amp;maxitems=MaxItems
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzonesbynamednsnamednsnameamphostedzoneidhostedzoneidampmaxitemsmaxitems-get-openapi.md
- name: AWS Route 53 API List Resource Record Sets
  x-api-slug: aws-route-53-api
  description: 'Lists the resource record sets in a specified hosted zone.            ListResourceRecordSets
    returns up to 100 resource record sets at a time in ASCII order, beginning at
    a position specified by the name and type elements. The action sorts results first
    by DNS name with the labels reversed, for example:            com.example.www.         Note
    the trailing dot, which can change the sort order in some circumstances.When multiple
    records have the same DNS name, the action sorts results by the record type.You
    can use the name and type elements to adjust the beginning position of the list
    of resource record sets returned:If you do not specify Name or TypeThe results
    begin with the first resource record set that the hosted zone contains.If you
    specify Name but not TypeThe results begin with the first resource record set
    in the list whose name is greater than or equal to Name.If you specify Type but
    not NameAmazon Route 53 returns the InvalidInput error.If you specify both Name
    and TypeThe results begin with the first resource record set in the list whose
    name is greater than or equal to Name, and whose type is greater than or equal
    to Type.This action returns the most current version of the records. This includes
    records that are PENDING, and that are not yet available on all Amazon Route 53
    DNS servers.To ensure that you get an accurate listing of the resource record
    sets for a hosted zone at a point in time, do not submit a ChangeResourceRecordSets
    request while you''re paging through the results of a ListResourceRecordSets request.
    If you do, some pages may display results without the latest changes while other
    pages display results with the latest changes.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/rrset&amp;identifier=StartRecordIdentifier&amp;maxitems=MaxItems?name=StartRecordName&amp;type=StartRecordType
  tags: Resource Record Sets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneidrrsetampidentifierstartrecordidentifierampmaxitemsmaxitemsnamestartrecordnameamptypestartrecordtype-get-openapi.md
- name: AWS Route 53 API List Reusable Delegation Sets
  x-api-slug: aws-route-53-api
  description: To retrieve a list of your reusable delegation sets, send a GET request
    tothe /2013-04-01/delegationset resource. The response to this request includes
    aDelegationSets element with zero, one, or multiple DelegationSetchild elements.
    By default, the list of delegation sets is displayed on a single page. You cancontrol
    the length of the page that is displayed by using the MaxItems parameter.You can
    use the Marker parameter to control the delegation set that the listbegins with.
    Note Amazon Route 53 returns a maximum of 100 items. If you set MaxItems to a
    value greater than100, Amazon Route 53 returns only the first 100.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/delegationset?marker=Marker&amp;maxitems=MaxItems
  tags: Reusable Delegation Sets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401delegationsetmarkermarkerampmaxitemsmaxitems-get-openapi.md
- name: AWS Route 53 API List Tags For Resource
  x-api-slug: aws-route-53-api
  description: Lists tags for one health check or hosted zone. For information about
    using tags for cost allocation, see Using Cost Allocation Tags in the AWS Billing
    and Cost Management User Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/tags/ResourceType/ResourceId
  tags: Tags
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401tagsresourcetyperesourceid-get-openapi.md
- name: AWS Route 53 API List Tags For Resources
  x-api-slug: aws-route-53-api
  description: Lists tags for up to 10 health checks or hosted zones.For information
    about using tags for cost allocation, see Using Cost Allocation Tags in the AWS
    Billing and Cost Management User Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/tags/ResourceType
  tags: Tags
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401tagsresourcetype-post-openapi.md
- name: AWS Route 53 API List Traffic Policies
  x-api-slug: aws-route-53-api
  description: 'Gets information about the latest version for every traffic policy
    that is associatedwith the current AWS account. Send a GET request to the /Amazon
    Route 53API version/trafficpolicy resource.Amazon Route 53 returns a maximum of
    100 items in each response. If you have a lot of trafficpolicies, you can use
    the maxitems parameter to list them in groups of up to100.The response includes
    three values that help you navigate from one group ofmaxitems traffic policies
    to the next:             IsTruncated           If the value of IsTruncated in
    the response is true,there are more traffic policies associated with the current
    AWS account.If IsTruncated is false, this response includes the lasttraffic policy
    that is associated with the current account.             TrafficPolicyIdMarker           If
    IsTruncated is true,TrafficPolicyIdMarker is the ID of the first traffic policy
    in the nextgroup of MaxItems traffic policies. If you want to list more trafficpolicies,
    make another call to ListTrafficPolicies, and specify the value ofthe TrafficPolicyIdMarker
    element from the response in theTrafficPolicyIdMarker request parameter.If IsTruncated
    is false, theTrafficPolicyIdMarker element is omitted from the response.             MaxItems           The
    value that you specified for the MaxItems parameter in the requestthat produced
    the current response.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicies&amp;maxitems=MaxItems?trafficpolicyid=TrafficPolicyIdMarker
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpoliciesampmaxitemsmaxitemstrafficpolicyidtrafficpolicyidmarker-get-openapi.md
- name: AWS Route 53 API List Traffic Policy Instances
  x-api-slug: aws-route-53-api
  description: 'Gets information about the traffic policy instances that you created
    by using thecurrent AWS account.NoteAfter you submit an UpdateTrafficPolicyInstance
    request, there''s a briefdelay while Amazon Route 53 creates the resource record
    sets that are specified in the traffic policydefinition. For more information,
    see the State response element.Send a GET request to the /Amazon Route 53 APIversion/trafficpolicyinstance
    resource.Amazon Route 53 returns a maximum of 100 items in each response. If you
    have a lot of trafficpolicy instances, you can use the MaxItems parameter to list
    them in groups of upto 100.The response includes five values that help you navigate
    from one group ofMaxItems traffic policy instances to the next:             IsTruncated           If
    the value of IsTruncated in the response is true,there are more traffic policy
    instances associated with the current AWSaccount.If IsTruncated is false, this
    response includes the lasttraffic policy instance that is associated with the
    current account.             MaxItems           The value that you specified for
    the MaxItems parameter in the requestthat produced the current response.                  HostedZoneIdMarker,
    TrafficPolicyInstanceNameMarker, and TrafficPolicyInstanceTypeMarker               If
    IsTruncated is true, these three values in theresponse represent the first traffic
    policy instance in the next group ofMaxItems traffic policy instances. To list
    more traffic policy instances,make another call to ListTrafficPolicyInstances,
    and specify these values inthe corresponding request parameters.If IsTruncated
    is false, all three elements are omittedfrom the response.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstances?hostedzoneid=HostedZoneIdMarker&amp;maxitems=MaxItems&amp;trafficpolicyinstancename=TrafficPolicyInstanceNameMarker&amp;trafficpolicyinstancetype=TrafficPolicyInstanceTypeMarker
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstanceshostedzoneidhostedzoneidmarkerampmaxitemsmaxitemsamptrafficpolicyinstancenametrafficpolicyinstancenamemarkeramptrafficpolicyinstancetypetrafficpolicyinstancetypemarker-get-openapi.md
- name: AWS Route 53 API List Traffic Policy Instances By Hosted Zone
  x-api-slug: aws-route-53-api
  description: 'Gets information about the traffic policy instances that you created
    in a specifiedhosted zone.NoteAfter you submit an UpdateTrafficPolicyInstance
    request, there''s a briefdelay while Amazon Route 53 creates the resource record
    sets that are specified in the traffic policydefinition. For more information,
    see the State response element.Send a GET request to the /Amazon Route 53 APIversion/trafficpolicyinstance
    resource and include the ID of the hostedzone.Amazon Route 53 returns a maximum
    of 100 items in each response. If you have a lot of trafficpolicy instances, you
    can use the MaxItems parameter to list them in groups of upto 100.The response
    includes four values that help you navigate from one group ofMaxItems traffic
    policy instances to the next:             IsTruncated               If the value
    of IsTruncated in the response is true, there aremore traffic policy instances
    associated with the current AWS account.If IsTruncated is false, this response
    includes the lasttraffic policy instance that is associated with the current account.             MaxItems           The
    value that you specified for the MaxItems parameter in the requestthat produced
    the current response.                  TrafficPolicyInstanceNameMarker and TrafficPolicyInstanceTypeMarker               If
    IsTruncated is true, these two values in the responserepresent the first traffic
    policy instance in the next group of MaxItemstraffic policy instances. To list
    more traffic policy instances, make another call toListTrafficPolicyInstancesByHostedZone,
    and specify these values in thecorresponding request parameters.If IsTruncated
    is false, all three elements are omittedfrom the response.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstances/hostedzone?id=HostedZoneId&amp;maxitems=MaxItems&amp;trafficpolicyinstancename=TrafficPolicyInstanceNameMarker&amp;trafficpolicyinstancetype=TrafficPolicyInstanceTypeMarker
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstanceshostedzoneidhostedzoneidampmaxitemsmaxitemsamptrafficpolicyinstancenametrafficpolicyinstancenamemarkeramptrafficpolicyinstancetypetrafficpolicyinstancetypemarker-get-openapi.md
- name: AWS Route 53 API List Traffic Policy Versions
  x-api-slug: aws-route-53-api
  description: 'Gets information about all of the versions for a specified traffic
    policy.Send a GET request to the /Amazon Route 53 APIversion/trafficpolicy resource
    and specify the ID of the traffic policyfor which you want to list versions.Amazon
    Route 53 returns a maximum of 100 items in each response. If you have a lot of
    trafficpolicies, you can use the maxitems parameter to list them in groups of
    up to100.The response includes three values that help you navigate from one group
    ofmaxitems traffic policies to the next:             IsTruncated           If
    the value of IsTruncated in the response is true,there are more traffic policy
    versions associated with the specified trafficpolicy.If IsTruncated is false,
    this response includes the lasttraffic policy version that is associated with
    the specified traffic policy.             TrafficPolicyVersionMarker           The
    ID of the next traffic policy version that is associated with the current AWSaccount.
    If you want to list more traffic policies, make another call toListTrafficPolicyVersions,
    and specify the value of theTrafficPolicyVersionMarker element in theTrafficPolicyVersionMarker
    request parameter.If IsTruncated is false, Amazon Route 53 omits theTrafficPolicyVersionMarker
    element from the response.             MaxItems           The value that you specified
    for the MaxItems parameter in the requestthat produced the current response.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicies/Id/versions&amp;maxitems=MaxItems?trafficpolicyversion=TrafficPolicyVersionMarker
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpoliciesidversionsampmaxitemsmaxitemstrafficpolicyversiontrafficpolicyversionmarker-get-openapi.md
- name: AWS Route 53 API List V P C Association Authorizations
  x-api-slug: aws-route-53-api
  description: 'Gets a list of the VPCs that were created by other accounts and that
    can be associated with a specified hosted zone because you''ve submitted one or
    more CreateVPCAssociationAuthorization requests. Send a GET request to the /2013-04-01/hostedzone/hosted
    zone ID/authorizevpcassociation resource. The response to this request includes
    a VPCs element with a VPC child element for each VPC that can be associated with
    the hosted zone.Amazon Route 53 returns up to 50 VPCs per page. To return fewer
    VPCs per page, include the MaxResults parameter:             /2013-04-01/hostedzone/hosted
    zone ID/authorizevpcassociation?MaxItems=VPCs per page                     If
    the response includes a NextToken element, there are more VPCs to list. To get
    the next page of VPCs, submit another ListVPCAssociationAuthorizations request,
    and include the value of the NextToken element from the response in the NextToken
    request parameter:            /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation?MaxItems=VPCs
    per page&amp;NextToken='
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id/authorizevpcassociation&amp;maxresults=MaxResults?nexttoken=NextToken
  tags: VPC
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneidauthorizevpcassociationampmaxresultsmaxresultsnexttokennexttoken-get-openapi.md
- name: AWS Route 53 API Test D N S Answer
  x-api-slug: aws-route-53-api
  description: Gets the value that Amazon Route 53 returns in response to a DNS request
    for a specified record name and type. You can optionally specify the IP address
    of a DNS resolver, an EDNS0 client subnet IP address, and a subnet mask.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/testdnsanswer&amp;edns0clientsubnetip=EDNS0ClientSubnetIP&amp;edns0clientsubnetmask=EDNS0ClientSubnetMask?hostedzoneid=HostedZoneId&amp;recordname=RecordName&amp;recordtype=RecordType&amp;resolverip=ResolverIP
  tags: DNS
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401testdnsanswerampedns0clientsubnetipedns0clientsubnetipampedns0clientsubnetmaskedns0clientsubnetmaskhostedzoneidhostedzoneidamprecordnamerecordnameamprecordtyperecordtypeampresolveripresolverip-get-openapi.md
- name: AWS Route 53 API Update Health Check
  x-api-slug: aws-route-53-api
  description: Updates an existing health check.Send a POST request to the /2013-04-01/healthcheck/health
    check ID             resource. Therequest body must include a document with an
    UpdateHealthCheckRequestelement. For more information about updating health checks,
    see Creating, Updating, and DeletingHealth Checks in the Amazon Route 53 Developer
    Guide.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/healthcheck/HealthCheckId
  tags: Checks,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401healthcheckhealthcheckid-post-openapi.md
- name: AWS Route 53 API Update Hosted Zone Comment
  x-api-slug: aws-route-53-api
  description: Updates the hosted zone comment. Send a POST request to the/2013-04-01/hostedzone/hosted
    zone ID             resource.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/hostedzone/Id
  tags: Hosted Zones
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401hostedzoneid-post-openapi.md
- name: AWS Route 53 API Update Traffic Policy Comment
  x-api-slug: aws-route-53-api
  description: Updates the comment for a specified traffic policy version.Send a POST
    request to the /2013-04-01/trafficpolicy/ resource.The request body must include
    a document with anUpdateTrafficPolicyCommentRequest element.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicy/Id/Version
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyidversion-post-openapi.md
- name: AWS Route 53 API Update Traffic Policy Instance
  x-api-slug: aws-route-53-api
  description: Updates the resource record sets in a specified hosted zone that were
    created based onthe settings in a specified traffic policy version.Send a POST
    request to the /2013-04-01/trafficpolicyinstance/traffic policy ID            resource.
    The request body must include a document with anUpdateTrafficPolicyInstanceRequest
    element.When you update a traffic policy instance, Amazon Route 53 continues to
    respond to DNS queriesfor the root resource record set name (such as example.com)
    while it replaces one group ofresource record sets with another. Amazon Route
    53 performs the following operations:Amazon Route 53 creates a new group of resource
    record sets based on the specified trafficpolicy. This is true regardless of how
    substantial the differences are between theexisting resource record sets and the
    new resource record sets. When all of the new resource record sets have been created,
    Amazon Route 53 starts to respondto DNS queries for the root resource record set
    name (such as example.com) by using thenew resource record sets.Amazon Route 53
    deletes the old group of resource record sets that are associated with theroot
    resource record set name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstance/Id
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstanceid-post-openapi.md
- name: AWS Route 53 API List Traffic Policy Instances By Policy
  x-api-slug: aws-route-53-api
  description: 'Gets information about the traffic policy instances that you created
    by using a specifytraffic policy version.NoteAfter you submit a CreateTrafficPolicyInstance
    or anUpdateTrafficPolicyInstance request, there''s a brief delay while Amazon
    Route 53creates the resource record sets that are specified in the traffic policy
    definition. Formore information, see the State response element.Send a GET request
    to the /Route 53 APIversion/trafficpolicyinstance resource and include the ID
    and version ofthe traffic policy.Amazon Route 53 returns a maximum of 100 items
    in each response. If you have a lot of trafficpolicy instances, you can use the
    MaxItems parameter to list them in groups of upto 100.The response includes five
    values that help you navigate from one group ofMaxItems traffic policy instances
    to the next:             IsTruncated               If the value of IsTruncated
    in the response is true,there are more traffic policy instances associated with
    the specified trafficpolicy.If IsTruncated is false, this response includes the
    lasttraffic policy instance that is associated with the specified traffic policy.             MaxItems               The
    value that you specified for the MaxItems parameter in the requestthat produced
    the current response.                  HostedZoneIdMarker, TrafficPolicyInstanceNameMarker,
    and TrafficPolicyInstanceTypeMarker               If IsTruncated is true, these
    values in the responserepresent the first traffic policy instance in the next
    group of MaxItemstraffic policy instances. To list more traffic policy instances,
    make another call toListTrafficPolicyInstancesByPolicy, and specify these values
    in thecorresponding request parameters.If IsTruncated is false, all three elements
    are omittedfrom the response.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: ://///2013-04-01/trafficpolicyinstances/trafficpolicy&amp;hostedzoneid=HostedZoneIdMarker?id=TrafficPolicyId&amp;maxitems=MaxItems&amp;trafficpolicyinstancename=TrafficPolicyInstanceNameMarker&amp;trafficpolicyinstancetype=TrafficPolicyInstanceTypeMarker&
  tags: Traffic Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/20130401trafficpolicyinstancestrafficpolicyamphostedzoneidhostedzoneidmarkeridtrafficpolicyidampmaxitemsmaxitemsamptrafficpolicyinstancenametrafficpolicyinstancenamemarkeramptrafficpolicyinstancetypetrafficpolicyinstancetypemarker-get-openapi.md
- name: AWS Route 53 API
  x-api-slug: aws-route-53-api
  description: Amazon Route 53 is a highly available and scalable cloud Domain Name
    System (DNS) web service. It is designed to give developers and businesses an
    extremely reliable and cost effective way to route end users to Internet applications
    by translating names like www.example.com into the numeric IP addresses like 192.0.2.1
    that computers use to connect to each other. Amazon Route 53 is fully compliant
    with IPv6 as well.Amazon Route 53 effectively connects user requests to infrastructure
    running in AWS &ndash; such as Amazon EC2 instances, Elastic Load Balancing load
    balancers, or Amazon S3 buckets &ndash; and can also be used to route users to
    infrastructure outside of AWS. You can use Amazon Route 53 to configure DNS health
    checks to route traffic to healthy endpoints or to independently monitor the health
    of your application and its endpoints. Amazon Route 53 Traffic Flow makes it easy
    for you to manage traffic globally through a variety of routing types, including
    Latency Based Routing, Geo DNS, and Weighted Round Robin&mdash;all of which can
    be combined with DNS Failover in order to enable a variety of low-latency, fault-tolerant
    architectures. Using Amazon Route 53 Traffic Flow&rsquo;s simple visual editor,
    you can easily manage how your end-users are routed to your application&rsquo;s
    endpoints&mdash;whether in a single AWS region or distributed around the globe.
    Amazon Route 53 also offers Domain Name Registration &ndash; you can purchase
    and manage domain names such as example.com and Amazon Route 53 will automatically
    configure DNS settings for your domains.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Networking_AmazonRoute53.png
  humanURL: https://aws.amazon.com/route53/
  baseURL: :///
  tags: AWS Route 53
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-route-53/master/_listings/aws-route-53/openapi.md
x-common:
- type: x-documentation
  url: http://docs.aws.amazon.com/Route53/latest/APIReference/
- type: x-faq
  url: https://aws.amazon.com/route53/faqs/
- type: x-forum
  url: https://forums.aws.amazon.com/forum.jspa?forumID=87
- type: x-pricing
  url: https://aws.amazon.com/route53/pricing/
- type: x-registrar-policies
  url: https://aws.amazon.com/route53/amazon-registrar-policies/
- type: x-service-health
  url: http://status.aws.amazon.com/
- type: x-service-level-agreement
  url: https://aws.amazon.com/route53/sla
- type: x-sla
  url: https://aws.amazon.com/route53/sla/
- type: x-website
  url: https://aws.amazon.com/route53/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---