# integracao-powerbi-mysql
Desafio de criação de relatório no Power BI através de banco de dados MySQL na Azure

QUESTÕES DO DESAFIO:

1) Diferença entre os recursos de “Acrescentar Consultas” e “Mesclar Consultas” no Power BI?

  Resposta: O recurso "Acrescentar Consultas" empilha as linhas das tabelas com estruturas iguais na vertical, já o recurso de "Mesclar Consultas" irá combinar as colunas na horizontal usando uma chave(id) em comum.

2) Por que no modelo adotado no banco de dados podemos apenas utilizar o "Mesclar" e não o "Atribuir"?
   Resposta: No caso em questão, não podemos utilizar o “Acrescentar consultas” pois o Power BI iria incluir novas linhas na tabela departamento e preencheria com informações somente as colunas que possuem dados na tabela localização, deixando as demais em branco. Isso não deixaria os dados organizados da maneira correta.


TRANSFORMAÇÕES FEITAS NA BASE DE DADOS:
1.	Verifique os cabeçalhos e tipos de dados
2.	Modifique os valores monetários para o tipo double preciso
3.	Verifique a existência dos nulos e analise a remoção
4.	Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente
5.	Verifique se há algum departamento sem gerente
6.	Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas
7.	Verifique o número de horas dos projetos
8.	Separar colunas complexas
9.	Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção
10.	Neste processo elimine as colunas desnecessárias. 
11.	Realize a junção dos colaboradores e respectivos nomes dos gerente . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.
12.	Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
13.	Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.
14.	Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir. (Vide "QUESTÕES DO DESAFIO"
15.	Agrupe os dados a fim de saber quantos colaboradores existem por gerente
16.	Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
