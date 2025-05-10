Docker Monitoring Stack
Uma stack de monitoramento profissional para ambientes Docker, utilizando Grafana, Loki, Prometheus, Node Exporter, cAdvisor e Promtail. Esta configuração é otimizada para produção, com limites de recursos para evitar sobrecarga do servidor.
Recursos

Grafana: Visualização de métricas e logs em dashboards personalizáveis.
Loki: Agregação de logs eficiente com indexação baseada em labels.
Prometheus: Coleta e armazenamento de métricas em tempo real.
Node Exporter: Métricas de hardware e sistema operacional.
cAdvisor: Monitoramento de uso de recursos de contêineres.
Promtail: Agente para coleta e envio de logs para o Loki.

Pré-requisitos

Docker 20.10+
Docker Compose 2.0+
Linux (Ubuntu 20.04+ recomendado)
4GB RAM, 2 CPUs, 50GB de disco

Instalação

Clone o repositório:
git clone https://github.com/seu-usuario/docker-monitoring-stack.git
cd docker-monitoring-stack


Crie os volumes persistentes:
mkdir -p volumes/{prometheus,grafana,loki}
sudo chown 10001:10001 volumes/loki
sudo chown 472:472 volumes/grafana


Inicie a stack:
docker-compose up -d


Acesse o Grafana em http://<seu-servidor>:3000 (login: admin/admin).


Configuração

Grafana: Configure fontes de dados em Configuration > Data Sources.
Prometheus: Adicione alvos de scraping em prometheus/prometheus.yml.
Loki: Ajuste retenção de logs em loki/loki-config.yaml.
Segurança: Altere credenciais padrão e configure um proxy reverso com SSL.

Uso

Crie dashboards no Grafana para visualizar métricas e logs.
Configure alertas no Prometheus para monitoramento proativo.
Use o Loki para consultar logs com LogQL.

Contribuição

Fork o repositório.
Crie uma branch (git checkout -b feature/nova-funcionalidade).
Commit suas alterações (git commit -m 'Adiciona nova funcionalidade').
Push para a branch (git push origin feature/nova-funcionalidade).
Abra um Pull Request.

Licença
Distribuído sob a licença MIT. Veja LICENSE para mais detalhes.
Contato
Para dúvidas ou sugestões, abra uma issue no repositório.
