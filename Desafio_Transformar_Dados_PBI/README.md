# Desafio Transformando Dados com Power BI 📊

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
