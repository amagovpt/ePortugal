## 8.	SOAP: Exemplo invocação do serviço remoto

[< voltar](https://amagovpt.github.io/ePortugal/area-reservada/)

A interação entre a Área Reservada do ePortugal e o sistema da Entidade AP remota inicia-se com uma invocação do webservice da Entidade com a seguinte estrutura:

<a href="https://github.com/amagovpt/ePortugal/blob/main/exemplos/Pedido.txt" target="_blank">Exemplo Pedido.txt - Request SOAP inicial</a>

```markdown
<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
	<SOAP-ENV:Header/>
	<S:Body>
		<ns2:getDataReservedAreaRequest xmlns:ns2="http://www.eportugal.gov.pt/reservedareakit/">
			<requestType>PEDIDOINICIAL{}</requestType>
			<ident/>123456789</ident/>
			<identType>NIC</identType>
		</ns2:getDataReservedAreaRequest>
	</S:Body>
</S:Envelope>
```

### Parâmetros de entrada:

| Nome do parâmetro | Descrição | Obrigatório | Lista de Valores (Chave – Descrição)
|--|--|--|-
| **requestType** | Tipo de pedido para obter um determinado tipo de informação | Sim | -
| **ident** | Identificador do utilizador, cidadão(nic), advogado(noa), solicitador(ncs) e notário(non) | Sim | -
| **identType** | Tipo de utilizador | Sim | CES:CT:000000001  - Cidadão português <br> CES:CT:000000014 - Advogado <br> CES:CT:000000015 - Solicitador <br> CES:CT:000000016 - Notário <br> CES:CT:000000100 - Cidadão Estrangeiro Europeu <br> CES:CT:000000200 - Cidadão Estrangeiro Não Europeu
| **orgIdent** | NIPC da pessoa colectiva | Não | -
| **lang** | Lingua actual do portal | Não | pt_PT<br>en_GB
