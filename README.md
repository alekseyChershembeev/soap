# Test soap application
example soap_spring from https://spring.io/guides/gs/producing-web-service/


1.)
`maven compile`(собирает скомпилированную xsd схему `~/soap/src/main/resources/countries.xsd` в java классы )

2.)тестируем тестовый запрос из `/root/IdeaProjects/soap/src/test/java/request/request.xml`

curl --header "content-type: text/xml" -d @request.xml http://localhost:8080/ws

3.) Результат должен быть таким :

`<?xml version="1.0"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header/>
  <SOAP-ENV:Body>
    <ns2:getCountryResponse xmlns:ns2="http://spring.io/guides/gs-producing-web-service">
      <ns2:country>
        <ns2:name>Spain</ns2:name>
        <ns2:population>46704314</ns2:population>
        <ns2:capital>Madrid</ns2:capital>
        <ns2:currency>EUR</ns2:currency>
      </ns2:country>
    </ns2:getCountryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>`
