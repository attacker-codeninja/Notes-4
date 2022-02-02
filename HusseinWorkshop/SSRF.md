# Exploit
  - Access local file (file:///)
  - Steal cloud secrets (aws, google cloud)
  - Port scan and discover internal host
  - Access private content

# Where
  - In parameter that takes URL as input and return the content
  - XXE

# Chaining
  - Open-redirect : to bypass restriction if the url must be on the same host
  - CLRF : same as open-redirect 

# Bypass
  - https://book.hacktricks.xyz/pentesting-web/ssrf-server-side-request-forgery
  - dns rebinding : 1u.ms (http://make-1.2.3.4-rebind-169.254.169.254-rr.1u.ms/)
  - domain redirection : test.com point to 127.0.0.1 for example
  - Enclosed alphanumerics 
  - 301 redirects
  - AWS will always drop anything after null byte %00
 
 
ipinfo.io to find the location of the server (EC2, gCloud ...)  
