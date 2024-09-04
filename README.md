
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

## Contribuições

Sinta-se à vontade para enviar pull requests ou abrir issues para reportar problemas ou sugerir melhorias.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais informações.

---

Agora você tem um novo projeto configurado para subir um ambiente de monitoramento no Minikube usando Ansible. Quando estiver pronto para começar, pode pedir mais detalhes ou ajustes!