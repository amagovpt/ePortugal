## 6.	Interação com a Entidade

[< voltar](https://amagovpt.github.io/ePortugal/area-reservada/)

Passo 1 – O utilizador autenticado entra na A.R., na página da Entidade A, onde está instalado e configurado o portlet:
-	O portlet invoca o serviço remoto da entidade identificando obrigatoriamente o cidadão, a língua escolhida e, opcionalmente, uma pessoa colectiva pré-seleccionada pelo utilizador; <br><br>
-	O serviço da entidade devolve vários blocos informativos em XML, por sua vez constituídos por sub-blocos que poderão conter informações diversas, links para “drill-down”, ou ações; <br><br>
-	Os blocos informativos são apresentados pelo portlet como “tabs” e os sub-blocos como seções dessas “tabs”, depois de transformados em HTML de acordo com o XSL pré-definido.

Passo 2 – O utilizador segue um dos links apresentados no Passo 1:
-	O portlet invoca o serviço representado por esse link e repete o processo de transformação e apresentação do XML recebido; <br><br>
-	Este passo pode ser repetido indefinidamente, consoante o que a instituição pretenda apresentar na A.R. do ePortugal.
