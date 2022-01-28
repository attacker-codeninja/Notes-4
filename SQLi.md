# Where

  - every parameter, header, or anything possibly runned through a database
  - In url (/add/user/123)
  - In graphQL query
  - test for blind SQLi which is more common
  - is this parameter process by a DB in the backend

## GraphQL

  - Test for introspection first
  - graphql burp plug-in : InQL
  
# Tools

  - SQLMap 
  - Atlas : SQLmap Tamper Script
  - Arjun : To find more potentially vulnerable parameter  
  
  
# Find website IP
  
   - https://viewdns.info/iphistory/ : view old ips for a website
   - SSRF (if the website is making request directly
   - https://bgp.he.net/ : check for all ip ranges own by company

# create bugs on the back-end

    "%BF" "%00" "%ff" '"><' weird unicode character (uniconvert)
  - host.com/?id=1 => host.com/?id[]=1           
         
