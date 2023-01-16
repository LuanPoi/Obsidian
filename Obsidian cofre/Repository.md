Tem como função ser uma abstração entre a camada de dados da aplicação e  a camada de [[ViewModel]].

O Repository vai ser o ponto de contato com as fontes de dados.

Tu pode escolher uma técnica entre:
- Web (sempre usa web);
- Cache (sempre usa Data Base);
- Cache Then web (carrega da base de dados e depois atualiza com Web);
- Web Then Cache (tenta buscar da web e soh busca do cache se falhar);