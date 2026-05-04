# Cloud-Native Container Security

<div align="center">
  <p>Elite B2B Security & Orchestration Configurations for Docker and Kubernetes (K8s).</p>
  <p>
    <a href="#-english">🇺🇸 English</a> | 
    <a href="#-português">🇧🇷 Português</a>
  </p>
</div>

---

## 🇺🇸 English

### Enterprise Container Orchestration
This repository contains the official **TAVARDT Agency** hardening templates for Cloud-Native infrastructure. Running applications in containers (Docker) or orchestrators (Kubernetes / Swarm) provides massive scalability, but default configurations are inherently insecure (running as root, unrestricted memory access). These templates are the gold standard for SOC2 and ISO 27001 compliant cloud deployments.

### Contents
- **`Dockerfile.hardened`**: A definitive Multi-Stage build template. It compiles applications in a heavy container but ships them in a minimal, Alpine/Scratch-based image. Crucially, it creates and enforces an unprivileged user (`UID 10001`), preventing root-level container breakouts.
- **`docker-compose.secure.yml`**: A production-grade Swarm/Compose template demonstrating Immutable Infrastructure (`read_only: true`), memory/CPU hard limits, and the dropping of all Linux kernel capabilities (`cap_drop: ALL`).
- **`k8s-pod-security.yaml`**: A Kubernetes Deployment manifest showcasing Pod Security Admission/Policies. It enforces `runAsNonRoot`, disables privilege escalation, and applies the `RuntimeDefault` seccomp profile to restrict malicious system calls.

### Implementation Guide
These templates are designed to be referenced and adapted by DevOps engineers when writing CI/CD pipelines. Never run untrusted code without dropping capabilities and enforcing read-only filesystems.

### Contact & Services
Looking for elite B2B infrastructure and high-ticket digital engineering?
- **Website:** [ag.tavardt.com](https://ag.tavardt.com/)
- **Email:** contact@tavardt.com

---

## 🇧🇷 Português

### Orquestração de Contêineres Corporativa
Este repositório contém os templates oficiais de "Hardening" (blindagem) da **TAVARDT** para infraestrutura Cloud-Native. Rodar aplicações em contêineres (Docker) ou orquestradores (Kubernetes / Swarm) oferece escalabilidade massiva, mas as configurações padrão são inerentemente inseguras (rodando como *root*, com acesso irrestrito à memória). Estes templates são o padrão ouro para *deploys* em nuvem compatíveis com auditorias B2B (SOC2, ISO 27001).

### Conteúdo
- **`Dockerfile.hardened`**: Um template definitivo de *Build* em Múltiplos Estágios (*Multi-Stage*). Ele compila a aplicação em um contêiner pesado, mas a entrega em uma imagem mínima baseada em Alpine/Scratch. Crucialmente, cria e impõe um usuário sem privilégios (`UID 10001`), prevenindo evasões de nível *root* do contêiner.
- **`docker-compose.secure.yml`**: Um template de produção para Swarm/Compose demonstrando Infraestrutura Imutável (`read_only: true`), limites rígidos de memória/CPU e o bloqueio de todas as capacidades do kernel Linux (`cap_drop: ALL`).
- **`k8s-pod-security.yaml`**: Um manifesto de *Deployment* do Kubernetes exibindo as *Pod Security Policies*. Ele obriga o parâmetro `runAsNonRoot`, desabilita a escalação de privilégios e aplica o perfil `RuntimeDefault` do *seccomp* para restringir chamadas de sistema (syscalls) maliciosas.

### Guia de Implementação
Estes templates foram desenhados para serem referenciados e adaptados por engenheiros de DevOps durante a escrita de *pipelines* de CI/CD. Nunca rode códigos não confiáveis sem remover as capacidades (capabilities) do Linux e impor sistemas de arquivos em modo leitura (*read-only*).

### Contato & Serviços
Procurando por infraestrutura B2B de elite e engenharia digital high-ticket?
- **Site:** [ag.tavardt.com/br/](https://ag.tavardt.com/br/)
- **E-mail:** contato@tavardt.com
