# Projeto-BDG

## Como importar o banco para visualizar no QGIS

    sudo apt-get install postgresql-10
    sudo apt-get install postgis
    sudo apt-get install postgresql-10-postgis-2.4
    sudo apt-get install qgis

    su - postgres
    createuser -d -E -i -l -P -r -s SEU_USER
    SUA_SENHA
    exit
    createdb NOME_DB -O SEU_USER
    psql -d NOME_DB -c "CREATE EXTENSION postgis;"
    sudo apt-get install pgadmin3

- Abra o pgAdmin III
- File/Add Server
  - Name: Nome_conexão
  - Host: localhost
  - Username: SEU_USER
  - Password: SUA SENHA
  - OK
- Clique em Nome_conexão duas vezes
- Clique em Databases duas vezes
- Botão direito em NOME_DB
  - Restore...
    - Filename: .../Projeto-BDG/Banco/banco.backup (esse arquivo ta na pasta Banco)
    - Vai dar um erro, ignora
    - Ver se as tabelas foram importadas clicando em NOME_DB/Schemas/public/Tables
- Abra o QGIS Desktop
- Botão direito em PostGIS
  - New Connection
    - Name: Nome_conexão (qualquer nome)
    - Host: localhost
    - Database: NOME_DB
    - Username: SEU_USER
    - Password: SUA_SENHA
    - Test connection
    - OK
  - Clique duas vezes em Nome_conexão
  - Faça o login se pedir
  - Clique em public
  - Arraste as tabelas pro Layers Panel (painel de baixo)
  - Vai aparecer a visualização

## Como criar novos layers

Baixar os dados (shapes) em: http://bhmap.pbh.gov.br/v2/mapa \
Siga esse tutorial: http://www.clickgeo.com.br/ebook-download-integracao-qgis-postgis/