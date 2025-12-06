DevOps Portfolio – Showcase
CI/CD com GitHub Actions • Docker • Kubernetes (kind) • Observabilidade

Este repositório é uma vitrine pública que apresenta meu projeto completo de CI/CD + Kubernetes, desenvolvido como portfólio profissional para demonstrar minhas habilidades práticas em DevOps.

O código-fonte real do projeto permanece em um repositório privado; aqui você encontrará a arquitetura, explicações, fluxos e evidências técnicas do que foi construído.

🚀 Visão Geral do Projeto

Este showcase demonstra:

Pipeline completo de CI/CD com GitHub Actions

Build multi-stage em Go

Build e push de imagem Docker para o Docker Hub

Deploy automatizado para um cluster Kubernetes local usando kind

Manifests Kubernetes declarativos (Deployment, Service, Namespace, Secrets)

Configuração de ambiente simulando um fluxo real de mercado

Estrutura preparada para expandir para AKS/EKS/OKE no futuro

🏗️ Arquitetura do Portfólio
                   ┌────────────────────┐
                   │     GitHub Repo     │
                   │  (Código Privado)   │
                   └─────────┬──────────┘
                             │ push
                             ▼
                 ┌───────────────────────┐
                 │     GitHub Actions    │
                 │  Pipeline CI/CD YAML  │
                 └─────────┬────────────┘
                           │
           Build           │            Deploy
    ┌────────────────┐     │     ┌──────────────────────┐
    │ Multi-stage Go  │─────┼────▶│ kubectl apply        │
    │ Dockerfile      │     │     │ Deploy no cluster    │
    └────────────────┘     │     │ kind (Kubernetes)     │
                           │     └──────────────────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Docker Hub (CI)   │
                └─────────────────────┘

⚙️ Pipeline CI/CD – Explicação Técnica

O pipeline é dividido em duas fases:

✔️ 1. Build Stage (CI)

Baixa o código

Compila a aplicação Go

Constrói imagem Docker multi-stage

Faz push da imagem para o Docker Hub

Usa tag automática baseada no GITHUB_SHA

✔️ 2. Deploy Stage (CD)

Conecta ao cluster kind

Aplica todos os manifests do diretório /k8s

Atualiza o Deployment com a nova imagem

Rola o deploy automaticamente

🐳 Docker – Build Multi-stage

Benefícios implementados:

Imagem final extremamente leve

Camadas otimizadas

Processo ideal para CI/CD com build rápido e seguro

☸️ Kubernetes (kind)

O cluster foi criado localmente com:

kind create cluster --name devops-portfolio --config kubeconfig-kind.yaml


Manifests utilizados:

namespace.yaml

deployment.yaml

service.yaml

Fluxo do deploy:

kubectl apply -f k8s/

📦 Estrutura do Projeto (Resumo)
DevOpsPortfolio (privado)
 │
 ├── .github/workflows/ci-cd.yaml   # Pipeline CI/CD completo
 ├── go-ci-cd-example/              # Aplicação Go (Hello-World)
 ├── k8s/                            # Manifests Kubernetes
 │   ├── deployment.yaml
 │   ├── service.yaml
 │   └── namespace.yaml
 └── Dockerfile                      # Build multi-stage

🧩 Competências Demonstradas

Kubernetes (kind)

GitHub Actions CI/CD

Docker & imagens multi-stage

GitHub Secrets

Deploy automatizado

Melhores práticas de DevOps

Infraestrutura declarativa (IaC-style com Kubernetes manifests)

🎯 Objetivo deste Repositório

Este repositório existe para:

Demonstrar experiência prática em DevOps

Servir como material de portfólio para recrutadores e clientes

Facilitar apresentação em entrevistas

Exibir domínio de CI/CD e Kubernetes de forma clara

📬 Contato

Se quiser saber mais sobre este projeto, colaborar ou contratar serviços DevOps:

LinkedIn: www.linkedin.com/in/vinicius-ferreira-bb86591a8

Email: vcostaferreira4@gmail.com
