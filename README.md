# IaC Pipeline: Terraform + GitHub Actions + Azure + Ansible

Projeto de automação de infraestrutura e configuração na Azure usando **Terraform** para o provisionamento e **Ansible** para o pós-provisionamento. A pipeline é executada via **GitHub Actions**.

## 💡 Objetivo

Provisionar e configurar uma máquina virtual Linux (Ubuntu) na Azure com:

- Recursos criados via Terraform:
  - Resource Group
  - Virtual Network (VNet)
  - Subnet
  - IP Público
  - NIC
  - Network Security Group com regras de acesso (SSH e porta 8081)
  - Máquina Virtual (VM) Ubuntu 20.04

- Configuração pós-provisionamento via Ansible:
  - Instalação do Docker
  - Deploy automático de aplicação Java (exemplo)
  - Outras dependências e pacotes

## ⚙️ Tecnologias utilizadas

- Terraform
- Ansible
- GitHub Actions
- Azure
- Linux / Bash scripting

## 📁 Estrutura do projeto

\`\`\`bash
.
├── .github/workflows/
│   └── deploy.yml
├── ansible/
│   ├── hosts
│   └── playbooks/
│       └── docker-api.yaml
├── main.tf
├── variables.tf
├── terraform.tfvars
├── backend.tf
└── README.md
\`\`\`

## 🚀 Como utilizar

### 1. Pré-requisitos

- Azure CLI instalado
- Terraform instalado
- Ansible instalado
- SSH configurado
- GitHub Secrets:
  - AZURE_CREDENTIALS
  - ARM_SUBSCRIPTION_ID (opcional)

### 2. Terraform: Provisionamento

\`\`\`bash
terraform init
terraform plan
terraform apply
\`\`\`

### 3. Ansible: Configuração da VM

\`\`\`bash
ansible-playbook -i ansible/hosts ansible/playbooks/docker-api.yaml
\`\`\`

### 4. Deploy automático

Push na branch principal dispara a pipeline via GitHub Actions.

## 👨‍💻 Autor

**Felipe Naliato Rodriguez**  
[GitHub](https://github.com/NRFelipe)

