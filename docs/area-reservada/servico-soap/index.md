## 7.	Serviço SOAP

Pode ser consultado o wsdl abaixo, que permite integração com a área reservada. Este wsdl terá que ser exposto pela AP Remota e integrar com a IAP. 

<a href="https://github.com/amagovpt/ePortugal/blob/main/exemplos/kitgenerico.wsdl" target="_blank">kitgenerico.wsdl</a>

```markdown
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<wsdl:definitions
	xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/"
	xmlns:wsp="http://www.w3.org/ns/ws-policy"
	xmlns:tns="http://www.eportugal.gov.pt/reservedareakit/"
	xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/"
	xmlns:xsd="http://www.w3.org/2001/XMLSchema" name="reservedareakit"
	targetNamespace="http://www.eportugal.gov.pt/reservedareakit/">
	<wsdl:types>
		<xsd:schema
			targetNamespace="http://www.eportugal.gov.pt/reservedareakit/">
			
			<xsd:element name="getDataReservedAreaRequest">
				<xsd:complexType>
					<xsd:sequence>
						<xsd:element name="requestType" type="xsd:string" />
						<xsd:element name="ident" type="xsd:string" />
						<xsd:element name="identType" type="xsd:string" />
						<xsd:element name="orgIdent" type="xsd:string" minOccurs="0"/>
						<xsd:element name="lang" type="xsd:string" minOccurs="0"/>
					</xsd:sequence>
				</xsd:complexType>
			</xsd:element>
			<xsd:element name="getDataReservedAreaResponse">
				<xsd:complexType>
					<xsd:sequence>
						<xsd:element name="reservedAreaDetail" type="tns:reservedAreaDetail" />
					</xsd:sequence>
				</xsd:complexType>
			</xsd:element>
			
			<xsd:complexType name="reservedAreaDetail">					
					<xsd:sequence>	
						<xsd:element name="name" type="xsd:string" />
						<xsd:element name="tabs" type="tns:tabs" />									
					</xsd:sequence>					
			</xsd:complexType>
			
			<xsd:complexType name="tabs">
				<xsd:sequence>
					<xsd:element name="tab" maxOccurs="unbounded" type="tns:tab" />
				</xsd:sequence>
			</xsd:complexType>
			
			<xsd:complexType name="tab">
				<xsd:sequence>		
                    <xsd:element name="tabNamePT" type="xsd:string" /> 
                    <xsd:element name="tabNameGB" type="xsd:string" /> 				
					<xsd:element name="xmlContentPT" type="xsd:string" />
					<xsd:element name="xmlContentGB" type="xsd:string" />																
				</xsd:sequence>
			</xsd:complexType>
		
		</xsd:schema>
	</wsdl:types>
	<wsdl:message name="getDataReservedAreaRequest">
		<wsdl:part name="parameters" element="tns:getDataReservedAreaRequest"></wsdl:part>
	</wsdl:message>
	<wsdl:message name="getDataReservedAreaResponse">
		<wsdl:part name="parameters" element="tns:getDataReservedAreaResponse"></wsdl:part>
	</wsdl:message>
	<wsdl:portType name="reservedareakit">
		<wsdl:operation name="getDataReservedArea">
			<wsdl:input message="tns:getDataReservedAreaRequest"></wsdl:input>
			<wsdl:output message="tns:getDataReservedAreaResponse"></wsdl:output>
		</wsdl:operation>
	</wsdl:portType>
	<wsdl:binding name="reservedareakitSOAP"
		type="tns:reservedareakit">
		<soap:binding style="document"
			transport="http://schemas.xmlsoap.org/soap/http" />
		<wsdl:operation name="getDataReservedArea">
			<soap:operation
				soapAction="http://www.eportugal.gov.pt/reservedareakit/getDataReservedArea" />
			<wsdl:input>
				<soap:body use="literal" />
			</wsdl:input>
			<wsdl:output>
				<soap:body use="literal" />
			</wsdl:output>
		</wsdl:operation>
	</wsdl:binding>
	<wsdl:service name="reservedareakit">
		<wsdl:port binding="tns:reservedareakitSOAP"
			name="reservedareakitSOAP">
			<soap:address location="http://172.31.201.82/reservedareakit/getDataReservedArea" />
		</wsdl:port>
	</wsdl:service>	
</wsdl:definitions>
```