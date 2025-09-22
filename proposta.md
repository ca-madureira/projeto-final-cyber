# PROPOSTA – Opção 2 (Consultoria)  
> Cliente: LojaZeta · Data: 2025‑09‑22

## 1. Sumário Executivo

A LojaZeta, e-commerce em expansão com infraestrutura em nuvem, enfrenta riscos críticos como ataques de SQL Injection, XSS e brute-force. A proposta visa implementar uma arquitetura de segurança em camadas, monitoramento centralizado mínimo viável e um plano de resposta a incidentes simples e eficaz. Espera-se ganhos como redução do tempo de detecção e resposta (MTTD/MTTR), aumento da cobertura de logs e mitigação de vulnerabilidades críticas com ações de curto prazo.

## 2. Escopo e Metodologia

**Escopo:**  
- Segurança de aplicação web e identidade  
- Monitoramento centralizado com alertas  
- Plano de resposta a incidentes  
- Roadmap de ações 30/90/180 dias  

**Metodologia:**  
- Análise baseada em boas práticas (OWASP, NIST)  
- Assunções: ambiente IaaS, acesso aos logs, colaboração do time técnico  
- Entrevistas com equipe, revisão de arquitetura atual, priorização por impacto/riscos

## 3. Arquitetura de Defesa (Camadas)

```mermaid
flowchart LR
  Internet --> WAF[WAF/CRS]
  WAF --> LB[Load Balancer]
  LB --> APP[App Node.js]
  APP --> DB[(PostgreSQL)]
  SIEM[Coleta/Correlação] -->|Logs| APP & DB
  IAM[Identidade] --> APP
