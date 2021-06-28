# https-poc


DESCRIPTION : This POC consists of two apps namely APP1 and APP2. APP1 is deployed on HTTP 8081 port and APP2 on HTTPS 8092 port (both deployed within VPC). APP1 then calls APP2 using a request component by using certificates.


Keystore generation command : keytool -genkey -alias mule -keyalg RSA -keystore keystore.jks -ext SAN="dns:<provide the url here>\
Export the certificate : keytool -export -alias mule -file client.cer -keystore keystore.jks&nbsp\
Generate truststore : keytool -import -v -trustcacerts -alias mule -file client.cer -keystore truststore.ts\
  
URLs: APP1 -> GET http://app1-test.us-e2.cloudhub.io/app1
      APP2 -> GET http://app2-test.us-e2.cloudhub.io/app2
  
