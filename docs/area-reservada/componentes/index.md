## 4.	Componentes da Arquitetura

[< voltar](https://amagovpt.github.io/ePortugal/area-reservada/)

Componentes ePortugal:
-	Um portlet de apresentação de informação da entidade, que requisita a informação à entidade por webservices SOAP, convertendo o XML recebido em HTML (incluindo componentes de back-end para comunicação e processamento dos dados da instituição); este portlet terá também um écran de configuração para configuração dos endpoints e user e password e carregamento do XSL. <br><br>
-	Uma descrição XSL de como devem ser apresentados os diversos blocos informativos ao utilizador, utlizada para construção do UI. 

Componentes na Entidade:
-	Um webservice SOAP que constrói as respostas ao pedido inicial e aos pedidos subsequentes, “linkados” na resposta ao pedido anterior (este webservice deverá estar acessível pela IAP).


