Lab SRE End-to-End

Este repositório documenta um laboratório prático de Site Reliability Engineering (SRE), construído do zero com foco em práticas reais de infraestrutura, conteinerização, orquestração, versionamento e observabilidade.

O objetivo do laboratório foi simular um fluxo completo de desenvolvimento, deploy e operação de uma aplicação em ambiente Kubernetes, utilizando ferramentas amplamente usadas no mercado.

---

## Tecnologias utilizadas

- Linux (Linux Mint + VM)
- Git e GitHub
- Docker
- Kubernetes (Minikube)
- Helm
- Terraform
- Ansible
- Python (API simples)
- Prometheus e Grafana (observabilidade)

---

## Estrutura do projeto

```text
.
├── app/            # Código da API em Python
├── docker/         # Dockerfile da aplicação
├── k8s/            # Manifests Kubernetes (raw)
├── helm/           # Helm Chart da aplicação
├── terraform/      # Infraestrutura como código
├── ansible/        # Automação de configuração
└── README.md

Etapas do laboratório
1. Base Linux e Git

    Organização do projeto

    Versionamento com Git

    Commits incrementais simulando fluxo real

2. Containerização

    Criação de Dockerfile

    Build e execução local da aplicação

    Versionamento de imagens

3. Kubernetes (manifests raw)

    Deployment

    Service (NodePort)

    Execução da aplicação no Minikube

4. Helm

    Criação de Helm Chart

    Simplificação de templates

    Deploy via Helm

    Upgrade e rollback de versões

5. Versionamento e controle de releases

    Uso de helm upgrade

    Uso de helm rollback

    Histórico de releases

6. Observabilidade

    Instalação de Prometheus e Grafana via Helm

    Exposição do Grafana

    Validação do stack de monitoramento

    Encerramento controlado do ambiente devido a limitações de recursos locais

Aprendizados principais

    Helm exige consistência total entre templates e values

    Observabilidade é pesada em ambientes locais

    Rollback é parte essencial da confiabilidade

    Infraestrutura deve ser reproduzível e descartável

    Problemas reais aparecem mesmo em laboratórios

Observação

Este laboratório foi executado em ambiente local (VM + Minikube).
Alguns componentes de observabilidade podem exigir mais recursos em ambientes de produção.

O ambiente local apresentou limitação de recursos para execução contínua da stack de observabilidade. A arquitetura foi validada e documentada, e a execução prática será retomada em ambiente com maior capacidade.