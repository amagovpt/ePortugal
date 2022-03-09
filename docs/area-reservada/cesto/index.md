## 18.	Link: Adicionar ao Cesto

[< voltar](https://amagovpt.github.io/ePortugal/area-reservada/)

O link de Adicionar ao Cesto permite adicionar um serviço ao Cesto do ePortugal. Esse serviço adicionado ao cesto será reencaminhado para a PMC pelo utilizador para realizar o serviço.
Neste tipo de link é sempre enviado o xml recebido para a PMC via ws para os casos que exista pré-preenchimento, nestes casos poderão adicionar ao xml os campos. Os formatos dos campos e estrutura terão que ser definidos entre a entidade e a PMC.


```markdown
<link>SERVICO[CES:SRV:000005462]</link>
```
*Exemplo de link adicionar ao Cesto*

```markdown
<DataFillForm>
	<Data>
		<Key>atributos_autenticacao</Key>
		<Value>CC|09848952</Value>  
	</Data>
		…
</DataFillForm>
```
*Exemplo de estrutura a adicionar no xml*