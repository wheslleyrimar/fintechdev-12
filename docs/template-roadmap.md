# Template de Roadmap Arquitetural Sustentável

Use este template como entregável do exercício da Aula 12. Preencha cada seção com base no cenário (fintech em crescimento, monólito modular, 2 times, deploy semanal, 5x usuários em 12 meses) ou em um contexto que o professor definir.

---

## 1. Contexto Atual

### Produto

| Item | Descrição |
|------|-----------|
| **Estágio** | (ex.: crescimento, consolidação, expansão) |
| **Criticidade** | (ex.: pagamentos = alta; notificações = média) |
| **Crescimento esperado** | (ex.: 5x usuários em 12 meses) |

### Organização

| Item | Descrição |
|------|-----------|
| **Número de times** | (ex.: 2 backend, 1 front) |
| **Senioridade** | (ex.: misto, predominância júnior/pleno) |
| **Gargalos organizacionais** | (ex.: deploy único, dependência entre times) |

---

## 2. Diagnóstico Técnico

### Arquitetura atual

| Item | Descrição |
|------|-----------|
| **Tipo** | monólito / híbrido / distribuído |
| **Principais acoplamentos** | (onde está o acoplamento forte?) |
| **Pontos frágeis conhecidos** | (deploy, domínio, integrações?) |

### Observabilidade

| Item | Descrição |
|------|-----------|
| **O que medimos bem?** | (métricas, logs, traces) |
| **O que não enxergamos?** | (gargalos, cauda, custo por request?) |

### Segurança

| Item | Descrição |
|------|-----------|
| **Identidade** | (como é feita? OAuth, API key, outro?) |
| **Dados sensíveis** | (classificação, criptografia, lifecycle?) |
| **Riscos conhecidos** | (pendências, dívida de segurança?) |

### Confiabilidade

| Item | Descrição |
|------|-----------|
| **SLO existe?** | (sim/não; se sim, qual?) |
| **Incidentes recorrentes?** | (quais tipos? disponibilidade, latência?) |

### Performance

| Item | Descrição |
|------|-----------|
| **Gargalos conhecidos?** | (banco, rede, CPU, terceiros?) |
| **Latência de cauda observada?** | (p99, p999; temos métrica?) |

### Custo

| Item | Descrição |
|------|-----------|
| **Custo crescente onde?** | (compute, banco, rede, observabilidade?) |
| **Desperdícios aparentes?** | (overprovision, fan-out, retries?) |

---

## 3. Principais Riscos (Top 5)

Preencha para cada risco: descrição técnica, impacto no negócio, probabilidade (alta/média/baixa) e mitigação proposta.

| # | Risco técnico | Impacto no negócio | Probabilidade | Mitigação proposta |
|---|----------------|--------------------|---------------|--------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | | |

---

## 4. Capacidades a Construir (não tecnologias)

Liste **capacidades** que a organização precisa ter (ex.: observabilidade padronizada, deploy mais frequente, comunicação assíncrona, SLOs claros, golden paths). Evite listar só nomes de ferramentas.

| # | Capacidade | Por que agora? |
|---|------------|----------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |

---

## 5. Roadmap em Fases

### Curto prazo (0–3 meses)

| Item | Descrição |
|------|-----------|
| **Foco** | (ex.: observabilidade, testes de carga, SLO inicial) |
| **Decisões** | (quais decisões arquiteturais tomamos?) |
| **Riscos mitigados** | (quais riscos do top 5 reduzimos?) |

### Médio prazo (3–6 meses)

| Item | Descrição |
|------|-----------|
| **Foco** | (ex.: deploy mais frequente, padrões, segurança) |
| **Decisões** | (quais decisões arquiteturais tomamos?) |
| **Riscos mitigados** | (quais riscos do top 5 reduzimos?) |

### Longo prazo (6–12 meses)

| Item | Descrição |
|------|-----------|
| **Foco** | (ex.: resiliência, custo, evolução de comunicação) |
| **Decisões** | (quais decisões arquiteturais tomamos?) |
| **Riscos mitigados** | (quais riscos do top 5 reduzimos?) |

---

## 6. Decisões Deliberadamente Adiadas

Liste decisões que **não** vamos tomar agora, com justificativa breve.

| Decisão adiada | Justificativa (por que não agora?) |
|----------------|------------------------------------|
| (ex.: migração completa para microsserviços) | (ex.: custo e risco altos; sinais de necessidade ainda insuficientes) |
| (ex.: multi-region) | |
| (ex.: refatorações profundas) | |

---

## 7. Trade-offs Explícitos

Declare o que estamos **aceitando** em troca de algo (ex.: mais latência para reduzir custo; menor autonomia inicial para ganhar consistência).

| Trade-off | O que aceitamos | O que ganhamos |
|-----------|-----------------|----------------|
| (ex.: aceitamos mais latência em X) | (ex.: latência p99 até Y ms) | (ex.: reduzir custo de Z) |
| | | |
| | | |

---

## 8. Critérios de Revisão do Roadmap

O roadmap deve ser revisado quando (marque ou descreva gatilhos):

- [ ] usuários crescerem X (defina X: ex. 2x em 6 meses)
- [ ] time dobrar (ou: novos times entrando)
- [ ] custo ultrapassar Y (defina Y ou % do orçamento)
- [ ] incidentes aumentarem (ex.: mais de N críticos por mês)
- [ ] contexto regulatório mudar (novos requisitos, auditoria)
- [ ] outro: _______________

---

*Arquitetura é equilíbrio contínuo, não ponto final. Este documento deve ser revisitado periodicamente.*
