# Exercícios — Aula 12: Jornada Arquitetural Completa

Este material é **didático**: além da tarefa, há **objetivo de aprendizado**, **passos sugeridos** e **dicas** para que o exercício consolide os conceitos da aula. Use o **[template-roadmap.md](template-roadmap.md)** como entregável.

---

# Exercício 1 — Construção de um Roadmap Arquitetural (principal)

## Objetivo de aprendizado

Fazer o aluno **pensar como arquiteto**, não como executor. O foco não é “acertar a arquitetura”, e sim:

- **Diagnosticar** o contexto (onde estamos, com que restrições).
- **Identificar** riscos técnicos reais (com base no cenário, não em opinião vaga).
- **Explicitar** trade-offs (o que estamos abrindo mão e por quê).
- **Propor** evolução sustentável (incremental, com critérios de revisão).

Ao final, o aluno deve conseguir **argumentar** cada decisão com base em contexto e trade-off, não em “achismo” ou modismo.

---

## Contexto do exercício (cenário base)

Você é responsável pela arquitetura de uma **fintech em crescimento**.

### Estado atual

- **Arquitetura:** monólito modular (módulos relativamente bem separados, mas um único deploy).
- **Organização:** 2 times de backend.
- **Deploy:** semanal (um pipeline, um artefato).
- **Testes:** poucos testes de carga; testes unitários e de integração em parte do código.
- **Observabilidade:** básica (logs, métricas simples, talvez health check); sem tracing estruturado ou SLO formal.
- **Custo:** cloud crescendo; ainda não há tagging fino por serviço/módulo.
- **Regulatório:** primeiros requisitos (ex.: LGPD, auditoria); nada ainda de BACEN pesado.

### Expectativa de crescimento (próximos 12 meses)

- **Usuários:** crescimento de até **5x**.
- **Times:** novos times entrando (mais squads, mais pessoas).
- **Integrações:** mais integrações externas (gateways, parceiros, data).
- **Confiabilidade:** maior pressão por estabilidade e rastreabilidade (negócio e regulatório).

---

## Tarefa do aluno

Construir um **roadmap arquitetural de 12 meses** que responda, de forma **explícita e justificada**:

1. **Onde estamos hoje?** (diagnóstico honesto: arquitetura, observabilidade, segurança, confiabilidade, performance, custo.)
2. **Quais são os maiores riscos técnicos?** (top 5, com impacto e mitigação.)
3. **O que NÃO devemos fazer agora?** (decisões deliberadamente adiadas e por quê.)
4. **O que precisamos construir como capacidade?** (não lista de tecnologias; ex.: “observabilidade padronizada”, “deploy mais frequente”.)
5. **Quais decisões podem ser adiadas?** (e sob que condição seriam revisitadas.)
6. **Quais trade-offs estamos aceitando?** (ex.: “aceitamos deploy semanal por mais N meses para priorizar X”.)

---

## Regras do exercício (para fixar os conceitos)

| Não vale | Vale |
|----------|------|
| “Reescrever tudo” (big rewrite) | Decisões **contextuais** (justificadas pelo cenário) |
| “Virar big tech” (copiar arquitetura de empresa grande) | **Trade-offs explícitos** (o que abrimos mão e por quê) |
| Copiar arquitetura famosa sem adaptar ao contexto | Roadmap **incremental** (fases curtas, revisão periódica) |

- Cada decisão deve ser **justificada** pelo contexto (estágio, time, custo, regulatório).
- Trade-offs devem ser **explícitos** no documento.
- O roadmap deve ter **fases** (ex.: 0–3, 3–6, 6–12 meses) e **critérios de revisão** (quando revisar o plano).

---

## Passos sugeridos (didáticos)

Seguir esta ordem ajuda a não pular o **diagnóstico** (erro comum) e a manter **contexto → riscos → capacidades → fases**.

1. **Ler o cenário** e listar, em tópicos, “o que temos hoje” e “o que está vindo” (crescimento, times, regulatório). Isso é o **contexto**.
2. **Diagnóstico:** Com base no [conceitos.md](conceitos.md) (maturação em camadas, observabilidade, segurança, custo), preencher: onde estamos fortes e onde estamos fracos. Não pule esta etapa — “roadmap sem diagnóstico é palpite”.
3. **Riscos:** Listar os 5 maiores riscos técnicos (ex.: deploy único com mais times, custo subindo sem visibilidade, falta de SLO). Para cada um: impacto no negócio, probabilidade (alta/média/baixa), mitigação proposta.
4. **Capacidades:** O que precisamos **construir** (observabilidade, deploy mais frequente, SLOs, padrões) — em termos de **capacidade**, não só “adotar tecnologia X”.
5. **O que NÃO fazer agora:** Listar 3–5 decisões que **deliberadamente** adiamos (ex.: migração completa para microsserviços, multi-region) e **justificar** (“por que não agora”; “revisitaremos quando Y”).
6. **Roadmap em fases:** Curto (0–3), médio (3–6), longo (6–12) — para cada fase: foco, decisões principais, riscos que essa fase mitiga.
7. **Trade-offs explícitos:** Escrever 3–5 trade-offs (o que aceitamos / o que ganhamos). Ex.: “Aceitamos deploy semanal por mais 6 meses para priorizar observabilidade e testes de carga.”
8. **Critérios de revisão:** Em que condições o roadmap deve ser revisitado? (ex.: usuários 2x, time dobrar, custo ultrapassar Z, incidentes críticos acima de N.)

Use o **[template-roadmap.md](template-roadmap.md)** para estruturar tudo.

---

## Dicas (para não cair em armadilhas comuns)

- **Evite começar por “vamos fazer microsserviços”.** Comece por diagnóstico: o que os dados e o dia a dia mostram? Só então veja se extrair um serviço (ou melhorar módulos) faz sentido em alguma fase.
- **Capacidades ≠ tecnologias.** “Observabilidade padronizada” é capacidade; “adotar Prometheus” é meio. O roadmap deve falar de **o que precisamos ter** (capacidade), não só de ferramentas.
- **Trade-off sem “o que abrimos mão” não é trade-off.** Sempre escreva: “Aceitamos X em troca de Y (até que Z aconteça).”
- **Critérios de revisão** evitam roadmap “congelado”. Defina gatilhos claros (crescimento, custo, incidentes, mudança regulatória).

---

## Entregável esperado

Um documento (preenchimento do template) contendo:

- **Contexto atual** (produto, organização).
- **Diagnóstico técnico** (arquitetura, observabilidade, segurança, confiabilidade, performance, custo).
- **Top 5 riscos** (com impacto, probabilidade, mitigação).
- **Capacidades a construir** (e por que agora).
- **Roadmap em fases** (0–3, 3–6, 6–12 meses: foco, decisões, riscos mitigados).
- **Decisões deliberadamente adiadas** (e justificativa).
- **Trade-offs explícitos** (o que aceitamos / o que ganhamos).
- **Critérios de revisão** (quando revisar o roadmap).

---

# Exercício 2 — Reflexão aprofundada (opcional)

Use **depois** de preencher o template, para fixar conceitos. As respostas podem ser curtas (1–2 parágrafos ou tópicos).

## 2.1 Trajetória e contexto

- Por que “arquitetura final” é considerada anti-pattern? Dê **um** exemplo concreto de consequência negativa.
- Cite **duas** variáveis de **contexto** que mudariam suas decisões no roadmap (ex.: tamanho do time, pressão regulatória). Explique em uma linha como cada uma afetaria o plano.

## 2.2 Momento de evoluir

- Quais **sinais técnicos** você usaria para decidir “é hora de evoluir o monólito” (ou de introduzir mais assincronia)? Liste pelo menos **três** e explique por que cada um é um sinal válido (e não opinião).
- Por que “evoluir antes do tempo cobra juros”? Relacione com **custo** e **complexidade** (operacional e cognitiva).

## 2.3 Roadmap e trade-offs

- Roadmap técnico **não** é “lista de tecnologias”. Em **três** linhas, o que ele **é**? (Use os conceitos: mitigação de riscos, capacidades, alinhamento com negócio.)
- Dê **um** exemplo de **trade-off explícito** que você incluiria no seu roadmap (ex.: “aceitamos mais latência para reduzir custo”). Escreva na forma: “Aceitamos X em troca de Y (até Z).”

## 2.4 Anti-patterns e papel do arquiteto

- Liste **dois** anti-patterns de jornada arquitetural e, em uma linha cada, **por que** são perigosos.
- Em **uma** frase: qual o papel do **arquiteto** na jornada? (O que ele deve fazer e o que **não** deve ser?)

---

## Respostas sugeridas (guia do professor)

- **2.1** Arquitetura final leva a overengineering, atraso e risco; exemplo: big rewrite que não entrega valor no prazo e contexto muda. Variáveis: tamanho do time (mais times → mais necessidade de boundaries), criticidade regulatória (mais requisitos → mais controles desde cedo), previsibilidade de demanda (pico previsível vs errático → estratégias de escala diferentes).
- **2.2** Sinais: conflitos frequentes de deploy (times se atropelando); domínio crescendo demais para um bounded context; gargalos localizados (uma parte precisa escalar diferente); times se bloqueando por acoplamento. Evoluir cedo aumenta complexidade operacional e custo sem retorno proporcional (mais serviços para operar, mais observabilidade necessária, curva de aprendizado).
- **2.3** Roadmap é: (1) mitigação de riscos — o que pode nos quebrar ou limitar; (2) construção de capacidades — o que precisamos saber fazer ou ter em pé; (3) alinhamento com negócio — prioridades técnicas atreladas a resultados. Trade-off exemplo: “Aceitamos deploy semanal por mais 6 meses em troca de priorizar observabilidade e testes de carga (revisitaremos quando o deploy virar gargalo ou o time dobrar).”
- **2.4** Anti-patterns: big rewrite (alto risco, longo prazo, contexto muda); copiar arquitetura de big tech (contexto diferente, complexidade e custo sem benefício). Arquiteto: facilita decisões e cria contexto para que os times tomem boas decisões; não é dono da verdade nem gargalo de decisão.

---

**Próximo passo:** preencher o [template-roadmap.md](template-roadmap.md) e revisar o [canvas-checklist.md](canvas-checklist.md) no encerramento da aula.
