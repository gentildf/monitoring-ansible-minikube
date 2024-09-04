
# Ambiente de Monitoramento com Ansible e Minikube

Este projeto contém um playbook Ansible para automatizar a instalação de um ambiente de monitoramento utilizando Prometheus e Grafana no Minikube.

## Estrutura do Projeto

```bash
monitoring-ansible-minikube/
├── inventories/
│   └── localhost.yml         # Inventário local para o Ansible
├── playbooks/
│   └── setup_monitoring.yml  # Playbook principal para configurar o monitoramento
├── roles/
│   ├── prometheus/           # Role para instalar Prometheus
│   ├── grafana/              # Role para instalar Grafana
│   └── common/               # Role para instalar pré-requisitos
└── README.md                 # Este arquivo
```

## Requisitos

- Minikube instalado
- Ansible instalado
- Helm instalado

## Como Usar

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/monitoring-ansible-minikube.git
   cd monitoring-ansible-minikube
   ```

2. Inicie o Minikube:

   ```bash
   minikube start
   ```

3. Execute o playbook:

   ```bash
   ansible-playbook -i inventories/localhost.yml playbooks/setup_monitoring.yml
   ```

4. Acesse o Grafana:

   Após a instalação, use o Minikube para abrir o Grafana no navegador:

   ```bash
   minikube service grafana --namespace monitoring
   ```

   Use o nome de usuário `admin` e a senha que será exibida no terminal.

## Testar o Ambiente de Monitoramento

1. **Acessar o Prometheus**:

   Após a instalação, use o Minikube para abrir o Prometheus no navegador:

   ```bash
   minikube service prometheus-server --namespace monitoring
   ```

   O Prometheus deve estar acessível em um navegador. Verifique se as métricas estão sendo coletadas corretamente.

2. **Acessar o Grafana**:

   Use o Minikube para acessar o Grafana no navegador:

   ```bash
   minikube service grafana --namespace monitoring
   ```

   Faça login no Grafana com o nome de usuário `admin` e a senha que foi exibida no terminal após a instalação.

3. **Adicionar Prometheus como Fonte de Dados no Grafana**:

   No Grafana:
   - Vá para **Configuration > Data Sources > Add data source**.
   - Selecione **Prometheus**.
   - Insira o endereço do Prometheus, que será algo como `http://prometheus-server.monitoring.svc.cluster.local:9090`.
   - Clique em **Save & Test**.

4. **Criar um Dashboard**:

   Após adicionar o Prometheus como fonte de dados, você pode criar um dashboard e adicionar gráficos para visualizar as métricas coletadas pelo Prometheus.

## Contribuições

Sinta-se à vontade para enviar pull requests ou abrir issues para reportar problemas ou sugerir melhorias.

---

Agora você tem um novo projeto configurado para subir um ambiente de monitoramento no Minikube usando Ansible.
Para ideias, sugestoes ou correções envie um email para gentiltechdf@gmail.com