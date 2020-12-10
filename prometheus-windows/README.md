## Prometheus e Windows

### Agents

Para coletar as métricas do sistema operacional, precisamos executar uma ferramenta chamada windows exporter, este é o responsável por entregar as informações no formato que o Prometheus espera, o agent é encontrado no link abaixo:

[Windows Exporter](https://github.com/prometheus-community/windows_exporter)

Após o download do release, basta executar e o endereço de coleta irá ester disponível para configuração no Prometheus.

### Execução

Para executar a aplicação será utilizado docker com docker-compose.

#### Subir o ambiente

```
docker-compose up -d
```

**Prometheus:** http://localhost:9090
**Grafana:** http://localhost:3000

### Configuração Prometheus

A configuração do Prometheus consiste na criação do arquivo **config/prometheus.yml**, onde será adicionado as configurações dos targets (No caso Windows Exporter)

### Configuração Grafana

Para visualizar as informações será utilizado o Grafana, dentro da configuração, temos o arquivo **config/grafana/datasource.yml**, este arquivo já cria um datasource com o Prometheus dentro do Grafana.

#### Admin Grafana

![Tela de Login Grafana](imgs/grafana_login.png?raw=true "Grafana")

O primeiro acesso no Grafana deve ser feito com o seguinte usuário:

**usuario:** admin
**senha:** admin

*Obs:* No primeiro acesso ele irá pedir para alterar a senha padrão.

Após autenticação temos acesso a tela inicial do Grafana:

![Grafana Tela Inicial](imgs/grafana_home.png?raw=true "Grafana")

#### Importação do Dashboard

Para visualizar os dados através de Dashboards do Grafana utilizar o seguinte Dash:

[Windows Node Dashboards](https://grafana.com/grafana/dashboards/2129)