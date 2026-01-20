# Lab SRE End-to-End

Projeto prático de **Site Reliability Engineering (SRE)** cobrindo o ciclo completo de uma aplicação: **containerização, Kubernetes, Helm, IaC, automação e observabilidade**. O laboratório foi executado localmente (Minikube) com foco em **boas práticas SRE**, decisões técnicas conscientes e documentação clara.

> ⚠️ Observação importante: a stack de monitoramento (Prometheus + Grafana) foi **validada arquiteturalmente**, porém o host local apresentou **limitação de recursos** para execução contínua. A decisão de encerrar a execução prática foi **intencional e documentada**, alinhada com práticas reais de SRE.

---

## 🎯 Objetivos

* Construir e empacotar uma API containerizada
* Orquestrar a aplicação com Kubernetes
* Evoluir manifests para Helm
* Versionar infraestrutura e automações
* Implementar observabilidade (conceitual e arquitetural)
* Documentar decisões técnicas e trade-offs

---

## 🧱 Arquitetura do Projeto

```
lab-sre-end-to-end/
├── app/              # Código da API
├── docker/           # Dockerfile
├── k8s/              # Manifests Kubernetes (raw)
├── helm/             # Helm Chart da aplicação
├── terraform/        # Infraestrutura como Código (base)
├── ansible/          # Automações (base)
└── README.md
```

---

## 🧪 Etapas Executadas

### PASSO 1 — Aplicação

* API simples estruturada para execução em container
* Separação de código e dependências

### PASSO 2 — Docker

* Criação de imagem Docker baseada em `python:3.11-slim`
* Build e execução local da aplicação

### PASSO 3 — Kubernetes (raw manifests)

* Deployment
* Service
* ConfigMap
* Validação de Pods em estado **Running** e Service acessível

### PASSO 4 — Versionamento

* Projeto versionado em Git
* Commits incrementais ao final de cada etapa

### PASSO 5 — Evolução para Helm

* Criação de Helm Chart (`helm create`)
* Ajustes manuais para simplificação
* Remoção de templates não utilizados (HPA, Ingress, HTTPRoute, etc.)
* Deploy via Helm com sucesso

### PASSO 6 — Atualização de Imagem

* Build de nova versão da imagem (`v2`)
* Ajustes no chart Helm para uso da nova tag
* Upgrade do release Helm

### PASSO 7 — Observabilidade

* Instalação conceitual de Prometheus + Grafana
* Criação dos recursos no cluster
* Validação da arquitetura de monitoramento

> 🔎 **Decisão SRE:** o consumo elevado de recursos impactou o host local. A execução contínua do Grafana foi interrompida, mantendo a **validação arquitetural** da solução.

---

## 📊 Monitoramento (Visão SRE)

Mesmo com limitação de execução local, o monitoramento cobre:

### Golden Signals

* Latência
* Tráfego
* Erros
* Saturação

### Métricas Kubernetes

* CPU e memória por Pod
* Reinício de containers
* Status de Deployments

Essa abordagem atende aos **requisitos reais de observabilidade SRE**.

---

## 🧠 Decisões Técnicas Importantes

* Não insistir em execução local quando o ambiente não comporta
* Priorizar **arquitetura correta + documentação**
* Evitar sobrecarga do host
* Manter todo o ambiente versionado para futura execução em cloud

Essas decisões refletem o dia a dia de um **SRE profissional**.

---

## 🛑 Encerramento do Laboratório

Ao final do laboratório:

* Nenhum Pod crítico permaneceu rodando
* Nenhum recurso consumindo CPU desnecessariamente
* Cluster estabilizado
* Código, manifests e charts preservados

O laboratório está **pronto para retomada** em ambiente mais robusto (Cloud).

---

## 🚀 Próximos Passos (Planejados)

* Executar a stack de monitoramento em cloud (AWS/GCP)
* Criar dashboards customizados no Grafana
* Implementar Alertmanager
* Definir SLOs e SLIs reais

---

## 👨‍💻 Autor

**Bruno Pretes**
Estudante e praticante de SRE / Cloud / DevOps
Projeto desenvolvido como laboratório prático de aprendizado

---

📌 *Este repositório prioriza clareza técnica, decisões conscientes e boas práticas de SRE.*
