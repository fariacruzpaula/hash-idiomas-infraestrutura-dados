## Infraestrutura de Dados de Escola de Idioma

### 1- Contexto de Negócio
A Hash Idiomas, uma escola que é focada no ensino de Inglês, Espanhol e Francês, está modernizando sua operação e decidiu digitalizar seus processos a fim de obter mais dados e clareza sobre suas vendas, clientes, receita etc. O desafio central é transformar a necessidade de controle operacional em uma infraestrutura de banco de dados relacional que suporte o crescimento da empresa.
Para resolver este case, será utilizada a linguagem SQL.

A estratégia de dados foi dividida em dois pilares: <br>
	• Integridade Operacional: garantir que alunos e cursos estejam devidamente vinculados às transações; <br>
	• Flexibilidade Comercial: permitir atualizações de preços e gestão de cancelamentos/reembolsos sem perda de histórico.

### 2- Implementação Técnica
A estrutura foi normalizada em três tabelas principais para evitar redundância e garantir a performance das consultas: <br>
			
|	 	Tabela			|				Descrição 			|
|-----------------------|-----------------------------------|
| Cursos 				| Produtos disponíveis				|
| Alunos 				| Cadastro centralizado de clientes |
| Vendas				| Histórico de vendas				|


### 3- Dicionário de Dados
Os tipos de dados utilizados para garantir eficiência, precisão e economia de de armazenamento são: 

| Coluna      	|	Tipo de Dado   |	         Descrição                        	|
|-------------	|------------------|--------------------------------------------	|
| nome_aluno  	| VARCHAR(50)      | Nome do aluno (Texto variável)         	  	|
| id_aluno	  	| INT		       | Identificador único (Primary Key)          	|
| email_aluno 	| VARCHAR(50)      | email do aluno (Texto variável) 	          	|
| id_curso    	| INT              | Identificador único (Primary Key) 				|
| nome_curso  	| VARCHAR(50)      | Idioma escolhido (Texto variável)          	|
| valor_curso 	| DECIMAL(10, 2)   | Valor monetário do curso                	  	|
| id_venda    	| INT              | Identificador único (Primary Key) 				|
| data_venda  	| DATE             | Data da venda	                             	|
| nome_professor|  VARCHAR(50)     | Nome do professor (Texto variável)          	|
| id_professor 	| INT              | Identificador único do professor (Primary Key) |



### 4 - Manipulação e Manutenção (DML)
O projeto contempla scripts para situações reais de mercado: <br>
	• Carga Inicial: Inserção de dados via INSERT INTO para popular o ecossistema; <br>
	• Atualização de Preços: Uso de UPDATE com cláusula WHERE específica (ex: reajuste do valor do curso) <br>
	• Gestão de Churn/Reembolso: Exclusão de registros de vendas canceladas via DELETE para manter o faturamento real atualizado. 

### 5 - Próximos passos
- Integridade Referencial: Implementar FOREIGN KEY para garantir a consistência entre as tabelas de vendas, cursos e alunos;
- Automação de IDs: Utilizar a propriedade IDENTITY(1,1) no SQL Server para automatizar o incremento de chaves primárias
- Camada de Abstração: Desenvolver VIEWS para consolidar dados dispersos, facilitando o consumo por ferramentas de BI ou usuários de negócio.


### 6 - Créditos
Este projeto foi desenvolvido e adaptado como parte do desafio prático de um curso Intensivo de SQL da Hashtag Treinamentos. 
	
