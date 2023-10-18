# Desafio Transformando Dados com Power BI 📊

#### Configuração Azure MySQL
Primeira ocorrência foi iniciar a configuração do ambiente de MySQL na [Azure Microsoft](https://azure.microsoft.com/pt-br/free/search/?ef_id=_k_Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB_k_&OCID=AIDcmmzmnb0182_SEM__k_Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB_k_&gclid=Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB).

#### Baixar scripts do gitHub para execução no MySQL
Após ambiente configurado, foi necessário acessar o [GitHub da Juliana Zanelatto](https://github.com/julianazanelatto/power_bi_analyst.git) localizado no folder Módulo 3. Utilizei o comando Git clone para baixar local os scripts.
- git clone https://github.com/julianazanelatto/power_bi_analyst.git

#### Conectar no MySQL Azure
Utilizando o Cloud Shell no Azure MySQL iniciei a sessão MySQL.
- mysql -h azuremydesafioprojeto01.mysql.database.azure.com -u desafiologicomysql -p "--ssl-ca=DigiCertGlobalRootCA.crt.pem";

- utilizando [script_bd_company.sql]() para criar DB azure_company;
- utilizando [insercao_de_dados_e_queries_sql.sql]() para inserção dos dados no DB criado com o script anterior;

#### Configuração Azure MySQL
Primeira ocorrência foi iniciar a configuração do ambiente de MySQL na [Azure Microsoft](https://azure.microsoft.com/pt-br/free/search/?ef_id=_k_Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB_k_&OCID=AIDcmmzmnb0182_SEM__k_Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB_k_&gclid=Cj0KCQjw4bipBhCyARIsAFsieCx6v8smNVMnqGW87eScxcK-g6l2zrTOdBStZnXg1a4vCEkf802gde8aAsS-EALw_wcB).

#### Baixar scripts do gitHub para execução no MySQL
Após ambiente configurado, foi necessário acessar o [GitHub da Juliana Zanelatto](https://github.com/julianazanelatto/power_bi_analyst.git) localizado no folder      Módulo 3. Utilizei o comando Git clone para baixar local os scripts.
- git clone https://github.com/julianazanelatto/power_bi_analyst.git

#### Conectar no MySQL Azure
Utilizando o Cloud Shell no Azure MySQL iniciei a sessão MySQL.
- mysql -h azuremydesafioprojeto01.mysql.database.azure.com -u desafiologicomysql -p "--ssl-ca=DigiCertGlobalRootCA.crt.pem";
    
- utilizando [script_bd_company.sql]() para criar DB azure_company;
- utilizando [insercao_de_dados_e_queries_sql.sql]() para inserção dos dados no DB criado com o script anterior;

#### Conectar Workbench no Azure MySQL
Para realizar esse passo, foi necessário pegar o passo-a-passo de conectar o Workbench no Azure MySQL. Seguindo as instruções, foi possível acessar a DB azure_company2 que foi criada via Azure MySQL.

#### Conectar Azure MySQL no Power BI
Para realizar este passo, foi necessário criar uma nova conexão via Power BI, com o conector MySQL. Assim com as credências do Azure MySQL, o Power BI teve acesso as bases do Azure.


#### Diretrizes para transformação dos dados

1. Verifique os cabeçalhos e tipos de dados
Muitas colunas vieram agrupadas em valores e Tabelas. Nome das colunas não muito sugestiveis.
2. Modifique os valores monetários para o tipo double preciso
Valor do salario alterado para decimal fixo na tabela employee. Não localizei outro campo referente a valor monetário. Sem dicionário de dados ficou complicado.
3. Verifique a existência dos nulos e analise a remoção
Localizei um NULL na inserção dos dados no campo Super_ssn, mas é algo que seja possível vir zerado. Demais casos localizados de NULL, são oriundos de cruzamentos que não encontram correspondência na base pesquisada.
4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente
Sim o employee James
5. Verifique se há algum departamento sem gerente
Não localizei
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/7ce1fcbe-d38f-4a51-bd7f-379e69d76aaa)
6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas
Não compreendi.
7. Verifique o número de horas dos projetos
select Pname, sum(Hours) as Total_hora from project, works_on where Pno = Pnumber group by Pname;
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/b3767dce-33de-4c4f-876d-328586e91c36)
8. Separar colunas complexas
Não entendi
9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção
No projeto power bi relatorio_DESAFIO_azure_MySQL_analisys.pbix criei a tabela EMPLOYEE_COM_DEPARTAMENTO
10. Neste processo elimine as colunas desnecessárias.
Criar novas tabelas?
11. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.
select e.Fname as Nome_employee, b.Manager from employee e
inner join (select e.Ssn, concat(e.Fname, ' ', e.Lname) as Manager from departament d, employee e where e.Ssn = d.Mgr_ssn) as b 
on b.Ssn = e.Super_ssn;
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/8a314fc3-03a2-475e-8cc9-ed5b5f6fbd0c)

12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
No projeto power bi relatorio_DESAFIO_azure_MySQL_analisys.pbix criei a tabela EMPLOYEE_COM_DEPARTAMENTO criei a coluna nome_completo
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/2d709776-ad24-442d-bb64-2f5843f3c9ab)
13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.
No projeto power bi relatorio_DESAFIO_azure_MySQL_analisys.pbix criei a tabela LOCATION_COM_DEPARTAMENTO
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/4f95241b-fe68-477d-a88d-74c1bcdc035a)
14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.
Porque mesclar faz a função do join no SQL e tem o comportamento esperado de atribuir um gerente ao colaborador.
15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente
São 7 colaboradores com gerente 1 está null
select e.Fname as Nome_employee, b.Manager from employee e
left join (select e.Ssn, concat(e.Fname, ' ', e.Lname) as Manager from departament d, employee e where e.Ssn = d.Mgr_ssn) as b 
on b.Ssn = e.Super_ssn;
![image](https://github.com/danLana/PBI_DIO_BOOTCAMP/assets/142463096/66bb3370-a7f8-45b6-a2b3-a9b4b11ae955)
16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
