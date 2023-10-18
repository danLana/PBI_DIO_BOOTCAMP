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
2. Modifique os valores monetários para o tipo double preciso

3. Verifique a existência dos nulos e analise a remoção

4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente

5. Verifique se há algum departamento sem gerente

6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas

7. Verifique o número de horas dos projetos

8. Separar colunas complexas

9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção

10. Neste processo elimine as colunas desnecessárias.

11. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.

12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores

13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.

14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.

15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente

16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
