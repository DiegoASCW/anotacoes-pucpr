https://docs.rapid7.com/insightidr/ports-used-by-insightidr/#collector-ports

|Source|Destination|Port|
|---|---|---|
|All deployed Collectors|data.insight.rapid7.com (US-1)  <br>  <br>us2.data.insight.rapid7.com (US-2)  <br>  <br>us3.data.insight.rapid7.com (US-3)  <br>  <br>eu.data.insight.rapid7.com (EMEA)  <br>  <br>ca.data.insight.rapid7.com (CA)  <br>  <br>au.data.insight.rapid7.com (AU)  <br>  <br>ap.data.insight.rapid7.com (AP)|443|
|All deployed Collectors|s3.amazonaws.com (US-1)  <br>  <br>s3.us-east-2.amazonaws.com (US-2)  <br>  <br>s3.us-west-2.amazonaws.com (US-3)  <br>  <br>s3.eu-central-1.amazonaws.com (EMEA)  <br>  <br>s3.ca-central-1.amazonaws.com (CA)  <br>  <br>s3.ap-southeast-2.amazonaws.com (AU)  <br>  <br>s3.ap-northeast-1.amazonaws.com (AP)|443|
|All Insight Agents if not connecting through a Collector|endpoint.ingress.rapid7.com (US-1)  <br>  <br>us2.endpoint.ingress.rapid7.com (US-2)  <br>  <br>us3.endpoint.ingress.rapid7.com (US-3)  <br>  <br>eu.endpoint.ingress.rapid7.com (EMEA)  <br>  <br>ca.endpoint.ingress.rapid7.com (CA)  <br>  <br>au.endpoint.ingress.rapid7.com (AU)  <br>  <br>ap.endpoint.ingress.rapid7.com (AP)|443|
|All Insight Agents if not connecting through a Collector|**US-1**  <br>  <br>us.storage.endpoint.ingress.rapid7.com  <br>  <br>us.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**US-2**  <br>  <br>us2.storage.endpoint.ingress.rapid7.com  <br>  <br>us2.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**US-3**  <br>  <br>us3.storage.endpoint.ingress.rapid7.com  <br>  <br>us3.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**EU**  <br>  <br>eu.storage.endpoint.ingress.rapid7.com  <br>  <br>eu.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**CA**  <br>  <br>ca.storage.endpoint.ingress.rapid7.com  <br>  <br>ca.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**AU**  <br>  <br>au.storage.endpoint.ingress.rapid7.com  <br>  <br>au.bootstrap.endpoint.ingress.rapid7.com  <br>  <br>**AP**  <br>  <br>ap.storage.endpoint.ingress.rapid7.com  <br>  <br>ap.bootstrap.endpoint.ingress.rapid7.com|443|
|All endpoints when using the Endpoint Monitor (Windows Only)|Collector|135 or 445 (WMI), 5508, 20000-30000|
|All Insight Agents (connecting through a Collector)|Collector|5508, 6608, 8037|
|Collector|Domain controller configured as LDAP source for LDAP event source|636 or 389|
|Collector|All domain controllers|135, 139, 445|
|Active Directory|WMI Collection Method|135, 445|
|DNS/DHCP, sometimes Active Directory|Windows File Share|139|
|Non-MS DHCP server|Collector|*UDP/TCP port above 1024|
|Firewall|Collector|*UDP/TCP port above 1024|
|Checkpoint Firewall|Collector|18184 or other as specified|
|VPN|Collector|*UDP/TCP port above 1024|
|AV Server (sending logs using syslog)|Collector|*UDP/TCP port above 1024|
|Nexpose/InsightVM|Collector|3780|
|Metasploit|Collector|3790|
|box.com logs|[https://api.box.com](https://api.box.com/)|443|