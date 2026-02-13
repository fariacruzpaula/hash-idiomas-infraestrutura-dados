<img src="lisa.jpg" width="800">

## Infraestrutura de Dados de Escola de Idioma

### 1- Contexto de Negócio
Este projeto simula a estruturação do ecossistema de dados para a Hash Idiomas, uma nova escola focada no ensino de Inglês, Espanhol e Francês. O desafio central foi transformar a necessidade de controle operacional em uma infraestrutura de banco de dados relacional que suporte o crescimento da empresa.

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

| Coluna      |	Tipo de Dado     |	Descrição                                 |
|-------------|------------------|--------------------------------------------|
| id_curso    | INT              | Identificador único (Primary Key)          |
| nome_curso  | VARCHAR(50)      | Nome do idioma (Texto variável)            |
| valor_curso | DECIMAL(5, 2)		 | Valor monetário                            |
| data_venda  | DATE             | Data da compra                             |


### 4 - Manipulação e Manutenção (DML)
O projeto contempla scripts para situações reais de mercado: <br>
	• Carga Inicial: Inserção de dados via INSERT INTO para popular o ecossistema; <br>
	• Atualização de Preços: Uso de UPDATE com cláusula WHERE específica (ex: reajuste do valor do curso) <br>
	• Gestão de Churn/Reembolso: Exclusão de registros de vendas canceladas via DELETE para manter o faturamento real atualizado. 
![lisa](https://github.com/user-attachments/assets/80272d7f-72f7-4e03-9bc4-c8839aaeb254)

### 5 - Créditos
Este projeto foi desenvolvido como parte do desafio prático de um curso Intensivo de SQL da Hashtag Treinamentos. 
	
