---
# Code generated by logshare-api. DO NOT EDIT.

title: HTTP requests
pcx_content_type: configuration
weight: 21
---

# HTTP requests

The descriptions below detail the fields available for `http_requests`.

{{<table-wrap>}}

| Field | Value | Type |
| -- | -- | -- |
| BotDetectionIDs | List of IDs that correlate to the Bot Management Heuristic detections made on a request. Available in Logpush v2 only. | array[int] |
| BotScore | Cloudflare Bot Score. Scores below 30 are commonly associated with automated traffic. Available for Bot Management customers (please contact your account team to enable). | int |
| BotScoreSrc | Detection engine responsible for generating the Bot Score. <br />Possible values are <em>Not Computed</em> \| <em>Heuristics</em> \| <em>Machine Learning</em> \| <em>Behavioral Analysis</em> \| <em>Verified Bot</em> \| <em>JS Fingerprinting</em> \| <em>Cloudflare Service</em>. | string |
| BotTags | Type of bot traffic (if available). Refer to [Bot Tags](/bots/concepts/cloudflare-bot-tags/) for the list of potential values. Available in Logpush v2 only. | array[string] |
| CacheCacheStatus | Cache status. <br />Possible values are <em>unknown</em> \| <em>miss</em> \| <em>expired</em> \| <em>updating</em> \| <em>stale</em> \| <em>hit</em> \| <em>ignored</em> \| <em>bypass</em> \| <em>revalidated</em> \| <em>dynamic</em> \| <em>stream_hit</em> \| <em>deferred</em> <br />"dynamic" means that a request is not eligible for cache. This can mean, for example that it was blocked by the firewall. Refer to [Cloudflare cache responses](/cache/about/default-cache-behavior/#cloudflare-cache-responses) for more details. | string |
| CacheReserveUsed | Cache Reserve was used to serve this request. Available in Logpush v2 only. | bool |
| CacheResponseBytes | Number of bytes returned by the cache. | int |
| CacheResponseStatus (deprecated) | HTTP status code returned by the cache to the edge. All requests (including non-cacheable ones) go through the cache. Refer also to CacheCacheStatus field. | int |
| CacheTieredFill | Tiered Cache was used to serve this request. | bool |
| ClientASN | Client AS number. | int |
| ClientCountry | 2-letter ISO-3166 country code of the client IP address. | string |
| ClientDeviceType | Client device type. | string |
| ClientIP | IP address of the client. | string |
| ClientIPClass | Client IP class. <br />Possible values are <em>unknown</em> \| <em>badHost</em> \| <em>searchEngine</em> \| <em>allowlist</em> \| <em>monitoringService</em> \| <em>noRecord</em> \| <em>scan</em> \| <em>tor</em>. | string |
| ClientMTLSAuthCertFingerprint | The SHA256 fingerprint of the certificate presented by the client during mTLS authentication. Only populated on the first request on an mTLS connection. Available in Logpush v2 only. | string |
| ClientMTLSAuthStatus | The status of mTLS authentication. Only populated on the first request on an mTLS connection. Available in Logpush v2 only. <br />Possible values are <em>unknown</em> \| <em>ok</em> \| <em>absent</em> \| <em>untrusted</em> \| <em>notyetvalid</em> \| <em>expired</em>. | string |
| ClientRegionCode | The ISO-3166-2 region code of the client IP address. | string |
| ClientRequestBytes | Number of bytes in the client request. | int |
| ClientRequestHost | Host requested by the client. | string |
| ClientRequestMethod | HTTP method of client request. | string |
| ClientRequestPath | URI path requested by the client. | string |
| ClientRequestProtocol | HTTP protocol of client request. | string |
| ClientRequestReferer | HTTP request referrer. | string |
| ClientRequestScheme | The URL scheme requested by the visitor. Available in Logpush v2 only. | string |
| ClientRequestSource | Identifies requests as coming from an external source or another service within Cloudflare. Refer to [ClientRequestSource field](/logs/reference/clientrequestsource/) for the list of potential values. Available in Logpush v2 only. | string |
| ClientRequestURI | URI requested by the client. | string |
| ClientRequestUserAgent | User agent reported by the client. | string |
| ClientSSLCipher | Client SSL cipher. | string |
| ClientSSLProtocol | Client SSL (TLS) protocol. The value "none" means that SSL was not used. | string |
| ClientSrcPort | Client source port. | int |
| ClientTCPRTTMs | The smoothed average of TCP round-trip time (SRTT). For the initial request on a connection, this is measured only during connection setup. For a subsequent request on the same connection, it is measured over the entire connection lifetime up until the time that request is received. Available in Logpush v2 only. | int |
| ClientXRequestedWith | X-Requested-With HTTP header. | string |
| ContentScanObjResults | List of content scan results. | array[string] |
| ContentScanObjTypes | List of content types. | array[string] |
| Cookies | String key-value pairs for Cookies. | object |
| EdgeCFConnectingO2O | True if the request looped through multiple zones on the Cloudflare edge. This is considered an orange to orange (o2o) request. Available in Logpush v2 only. | bool |
| EdgeColoCode | IATA airport code of data center that received the request. | string |
| EdgeColoID | Cloudflare edge colo id. | int |
| EdgeEndTimestamp | Timestamp at which the edge finished sending response to the client. | int or string |
| EdgePathingOp | Indicates what type of response was issued for this request (unknown = no specific action). | string |
| EdgePathingSrc | Details how the request was classified based on security checks (unknown = no specific classification). | string |
| EdgePathingStatus | Indicates what data was used to determine the handling of this request (unknown = no data). | string |
| EdgeRateLimitAction | The action taken by the blocking rule; empty if no action taken. <br />Possible values are <em>unknown</em> \| <em>simulate</em> \| <em>ban</em> \| <em>challenge</em> \| <em>jsChallenge</em>. | string |
| EdgeRateLimitID | The internal rule ID of the rate-limiting rule that triggered a block (ban) or log action. 0 if no action taken. | int |
| EdgeRequestHost | Host header on the request from the edge to the origin. | string |
| EdgeResponseBodyBytes | Size of the HTTP response body returned to clients. Available in Logpush v2 only. | int |
| EdgeResponseBytes | Number of bytes returned by the edge to the client. | int |
| EdgeResponseCompressionRatio | Edge response compression ratio. | float |
| EdgeResponseContentType | Edge response Content-Type header value. | string |
| EdgeResponseStatus | HTTP status code returned by Cloudflare to the client. | int |
| EdgeServerIP | IP of the edge server making a request to the origin. Possible responses are string in IPv4 or IPv6 format, or empty string. Empty string means that there was no request made to the origin server. | string |
| EdgeStartTimestamp | Timestamp at which the edge received request from the client. | int or string |
| EdgeTimeToFirstByteMs | Total view of Time To First Byte as measured at Cloudflare's edge. Starts after a TCP connection is established and ends when Cloudflare begins returning the first byte of a response to eyeballs. Includes TLS handshake time (for new connections) and origin response time. Available in Logpush v2 only. | int |
| FirewallMatchesActions | Array of actions the Cloudflare firewall products performed on this request. The individual firewall products associated with this action be found in FirewallMatchesSources and their respective RuleIds can be found in FirewallMatchesRuleIDs. The length of the array is the same as FirewallMatchesRuleIDs and FirewallMatchesSources. <br />Possible actions are <em>unknown</em> \| <em>allow</em> \| <em>block</em> \| <em>challenge</em> \| <em>jschallenge</em> \| <em>log</em> \| <em>connectionClose</em> \| <em>challengeSolved</em> \| <em>challengeFailed</em> \| <em>challengeBypassed</em> \| <em>jschallengeSolved</em> \| <em>jschallengeFailed</em> \| <em>jschallengeBypassed</em> \| <em>bypass</em> \| <em>managedChallenge</em> \| <em>managedChallengeSkipped</em> \| <em>managedChallengeNonInteractiveSolved</em> \| <em>managedChallengeInteractiveSolved</em> \| <em>managedChallengeBypassed</em>. | array[string] |
| FirewallMatchesRuleIDs | Array of RuleIDs of the firewall product that has matched the request. The firewall product associated with the RuleID can be found in FirewallMatchesSources. The length of the array is the same as FirewallMatchesActions and FirewallMatchesSources. | array[string] |
| FirewallMatchesSources | The firewall products that matched the request. The same product can appear multiple times, which indicates different rules or actions that were activated. The RuleIDs can be found in FirewallMatchesRuleIDs, the actions can be found in FirewallMatchesActions. The length of the array is the same as FirewallMatchesRuleIDs and FirewallMatchesActions. <br />Possible sources are <em>unknown</em> \| <em>asn</em> \| <em>country</em> \| <em>ip</em> \| <em>ipRange</em> \| <em>securityLevel</em> \| <em>zoneLockdown</em> \| <em>waf</em> \| <em>firewallRules</em> \| <em>uaBlock</em> \| <em>rateLimit</em> \| <em>bic</em> \| <em>hot</em> \| <em>l7ddos</em> \| <em>botFight</em> \| <em>apiShield</em> \| <em>botManagement</em> \| <em>dlp</em> \| <em>firewallManaged</em> \| <em>firewallCustom</em>. | array[string] |
| JA3Hash | The MD5 hash of the JA3 fingerprint used to profile SSL/TLS clients. Available in Logpush v2 only. | string |
| OriginDNSResponseTimeMs | Time taken to receive a DNS response for an origin name. Usually takes a few milliseconds, but may be longer if a CNAME record is used. Available in Logpush v2 only. | int |
| OriginIP | IP of the origin server. | string |
| OriginRequestHeaderSendDurationMs | Time taken to send request headers to origin after establishing a connection. Note that this value is usually 0. Available in Logpush v2 only. | int |
| OriginResponseBytes (deprecated) | Number of bytes returned by the origin server. | int |
| OriginResponseDurationMs | Upstream response time, measured from the first datacenter that receives a request. Includes time taken by Argo Smart Routing and Tiered Cache, plus time to connect and receive a response from origin servers. This field replaces OriginResponseTime. Available in Logpush v2 only. | int |
| OriginResponseHTTPExpires | Value of the origin 'expires' header in RFC1123 format. | string |
| OriginResponseHTTPLastModified | Value of the origin 'last-modified' header in RFC1123 format. | string |
| OriginResponseHeaderReceiveDurationMs | Time taken for origin to return response headers after Cloudflare finishes sending request headers. Available in Logpush v2 only. | int |
| OriginResponseStatus | Status returned by the origin server. The value 0 means that there was no request made to the origin server and the response was served by Cloudflare's Edge. | int |
| OriginResponseTime (deprecated) | Number of nanoseconds it took the origin to return the response to edge. | int |
| OriginSSLProtocol | SSL (TLS) protocol used to connect to the origin. | string |
| OriginTCPHandshakeDurationMs | Time taken to complete TCP handshake with origin. This will be 0 if an origin connection is reused. Available in Logpush v2 only. | int |
| OriginTLSHandshakeDurationMs | Time taken to complete TLS handshake with origin. This will be 0 if an origin connection is reused. Available in Logpush v2 only. | int |
| ParentRayID | Ray ID of the parent request if this request was made using a Worker script. | string |
| RayID | ID of the request. | string |
| RequestHeaders | String key-value pairs for RequestHeaders. | object |
| ResponseHeaders | String key-value pairs for ResponseHeaders. | object |
| SecurityLevel | The security level configured at the time of this request. This is used to determine the sensitivity of the IP Reputation system. | string |
| SmartRouteColoID | The Cloudflare datacenter used to connect to the origin server if Argo Smart Routing is used. Available in Logpush v2 only. | int |
| UpperTierColoID | The "upper tier" datacenter that was checked for a cached copy if Tiered Cache is used. Available in Logpush v2 only. | int |
| WAFAction | Action taken by the WAF, if triggered. | string |
| WAFAttackScore | Overall request score generated by the WAF detection module. | int |
| WAFFlags (deprecated) | Additional configuration flags: <em>simulate (0x1)</em> \| <em>null</em>. | string |
| WAFMatchedVar (deprecated) | The full name of the most-recently matched variable. | string |
| WAFProfile | WAF profile. <br />Possible values are <em>low</em> \| <em>med</em> \| <em>high</em>. | string |
| WAFRCEAttackScore | WAF score for an RCE attack. | int |
| WAFRuleID | ID of the applied WAF rule. | string |
| WAFRuleMessage | Rule message associated with the triggered rule. | string |
| WAFSQLiAttackScore | WAF score for an SQLi attack. | int |
| WAFXSSAttackScore | WAF score for an XSS attack. | int |
| WorkerCPUTime | Amount of time in microseconds spent executing a worker, if any. | int |
| WorkerStatus | Status returned from worker daemon. | string |
| WorkerSubrequest | Whether or not this request was a worker subrequest. | bool |
| WorkerSubrequestCount | Number of subrequests issued by a worker when handling this request. | int |
| WorkerWallTimeUs | Real-time in microseconds elapsed between start and end of worker invocation. | int |
| ZoneName | The human-readable name of the zone (e.g. 'cloudflare.com'). Available in Logpush v2 only. | string |

{{</table-wrap>}}