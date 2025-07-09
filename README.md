# AUTOMAÇÃO N8N

Este projeto utiliza o [n8n](https://n8n.io/), uma plataforma de automação de workflows, para monitorar feeds de notícias sobre promoções de passagens aéreas e enviar alertas via Telegram.

## Funcionalidades

- **Monitoramento de Feeds RSS**: Busca notícias em sites como Pontos pra Voar, Passageiro de Primeira e Melhores Destinos.
- **Filtro Inteligente**: Filtra posts que mencionam cidades de interesse e promoções com milhas.
- **Alertas no Telegram**: Envia mensagens automáticas para um chat do Telegram quando uma possível promoção é encontrada.
- **Gestão de Erros**: Notifica no Telegram caso algum erro ocorra durante a execução do workflow.

## Estrutura do Projeto

- `docker-compose.yml`: Arquivo para subir o ambiente n8n via Docker.
- `alertas.json`: Workflow do n8n para monitoramento e alertas de promoções.
- `dados-n8n/`: Diretório persistente de dados do n8n (logs, banco de dados, configurações, nodes customizados).

## Como rodar o projeto

1. **Pré-requisitos**:
   - [Docker](https://www.docker.com/) instalado.

2. **Subir o ambiente**:
   ```sh
   docker-compose up -d
   ```

3. **Acessar o n8n**:
   - Abra o navegador e acesse: [http://localhost:5678](http://localhost:5678)
   - Usuário: `danielquimicah@hotmail.com`
   - Senha: `Daniel@1993`

4. **Importar o workflow**:
   - No painel do n8n, importe o arquivo `alertas.json` para ativar o fluxo de alertas.

## Observações

- Os dados do n8n são persistidos na pasta `dados-n8n/`.
- O workflow pode ser customizado para monitorar outras cidades ou canais do Telegram.
- As credenciais do Telegram devem ser configuradas no painel do n8n. 