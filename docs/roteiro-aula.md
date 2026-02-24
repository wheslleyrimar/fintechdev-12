# Roteiro da Aula 12 — Jornada Arquitetural Completa

Roteiro **didático** para o professor: como conduzir a aula, como explicar cada bloco de conceitos, quais perguntas usar para provocar reflexão e como evitar que a aula vire só “teoria”.

---

## Tema central

**Arquitetura não é estado, é trajetória.**  
Consolidação da jornada arquitetural e construção de um roadmap técnico sustentável. O foco é **reflexão e critérios de decisão**, não execução de lab.

---

## Objetivo da aula (o que validar ao final)

O aluno deve sair com:

- **Critérios** para decidir quando e como evoluir (sinais técnicos reais, não hype).
- **Entendimento** de trade-offs explícitos (o que abrimos mão e por quê).
- **Capacidade** de construir um roadmap com diagnóstico, fases, riscos e critérios de revisão.
- **Consciência** para evitar overengineering e modismo.
- **Mentalidade** de arquitetura como **jornada**, não como destino.

**Frase de sucesso:** *"Agora sei como pensar arquitetura ao longo do tempo."*

**Sinal de falha:** Aluno acha que existe “arquitetura final”, “stack ideal” ou que basta copiar big tech.

---

## Como conduzir a aula (orientação didática)

### 1. Revisitar as aulas anteriores de forma conectada

Não liste só “o que vimos”. **Conecte** cada tema à ideia de **jornada** e **contexto**:

| Tema (aula anterior) | Conexão com “jornada” |
|----------------------|------------------------|
| Comunicação (síncrona vs eventos, fan-out) | A escolha de como serviços se comunicam **muda** ao longo do tempo; começar síncrono e introduzir eventos onde faz sentido é evolução, não “erro do passado”. |
| Observabilidade | É **pré-condição** para evoluir com segurança; sem ela, “evoluir” é chute. |
| SRE (SLO, error budget) | Confiabilidade é **compromisso explícito** que evolui com o produto (MVP pode ter SLO mais frouxo; produto maduro exige SLO rígido). |
| Performance (latência, cauda) | Performance é **propriedade sistêmica**; medir antes de “otimizar” evita trabalho no lugar errado. |
| FinOps (custo) | Custo é **feedback** da arquitetura; roadmap deve considerar onde o custo está e por quê. |
| Segurança | É **fundação**, não fase; em fintech não dá para adicionar “depois”. |
| Padrões e governança | São o que permite **escalar** a arquitetura na organização (não só no código). |

**Mensagem para enfatizar:** Nada disso é “fase única”; tudo se desdobra ao longo do tempo e do contexto. A aula 12 **amarra** esses fios em “como pensar a evolução” e “como construir um roadmap”.

### 2. Provocar reflexão, não resposta única

- **Evite** perguntas com “resposta certa” única (ex.: “O que é SLO?”).
- **Prefira** perguntas que exigem **decisão** e **justificativa**:
  - *“No cenário do exercício, em que momento faria sentido evoluir o monólito? Com base em qual sinal?”*
  - *“Que trade-off você está aceitando ao escolher manter deploy semanal por mais 6 meses?”*
  - *“O que você deliberadamente NÃO faria agora no roadmap, e por quê?”*
- **Peça decisões** (com contexto e trade-off), não definições de conceito.

### 3. Usar exemplos concretos (não genéricos)

- **Big rewrite que falhou** — Ex.: Netscape (rewrite atrasou, mercado mudou), ou casos públicos de empresas que tentaram “reescrever tudo” e cancelaram ou atrasaram anos.
- **Monólito que escalou** — Ex.: Shopify, Basecamp (ou outros que mantiveram monólito bem modularizado por muito tempo antes de extrair serviços).
- **Fintech e regulatório** — Ex.: decisões que tiveram que ser “retrofitadas” porque segurança ou auditoria foram pensadas depois.
- **Copiar arquitetura** — Ex.: “Fomos para Kafka porque todo mundo usa” sem problema de escala ou assincronia claro; resultado: complexidade e custo sem benefício.

Se você tiver **casos reais** (anonimizados) da sua experiência, use-os — eles fixam muito mais que exemplos genéricos.

### 4. Trabalhar o documento mestre (conceitos.md)

- O **[conceitos.md](conceitos.md)** está em **versão aprofundada e didática**: cada tópico tem “o que é”, “por que importa”, “como se manifesta” e “como aplicar”.
- **Sugestão:** Não leia o documento inteiro em aula. Use como **base para falar** e destaque:
  - **Parte I** — Arquitetura como trajetória; erro de “estado final”; contexto.
  - **Parte II** — Monólito bem projetado; sinais para evoluir.
  - **Parte III** — Comunicação, observabilidade, segurança, confiabilidade, performance, custo (revisão com foco em “eixo da evolução”).
  - **Parte IV** — Padrões, golden path, governança, Conway.
  - **Parte V** — Maturidade em camadas, roadmap, trade-offs, anti-patterns, papel do arquiteto, prática contínua.
- Indique que a **leitura completa** é pós-aula para quem quiser aprofundar.

### 5. Exercício final — Roadmap arquitetural

- Contexto e regras em **[exercicios.md](exercicios.md)**; entregável em **[template-roadmap.md](template-roadmap.md)**.
- **Regras a frisar:** Decisões contextuais; trade-offs explícitos; incremental. Não vale big rewrite, “virar big tech” nem copiar arquitetura famosa.
- **Didática:** Antes de preencher, peça que respondam em 2 minutos: *“Qual o maior risco técnico hoje no cenário? E qual decisão você NÃO tomaria agora?”* Isso força diagnóstico e “decisões adiadas” antes de preencher o template.
- Pode ser em **grupo** ou **individual**; o importante é **argumentar** diagnóstico, riscos, decisões adiadas e trade-offs. Na discussão, peça que um grupo apresente o “diagnóstico” e outro o “o que não fazer agora”; compare com o que o conceitos.md recomenda.

### 6. Encerramento com Canvas e Checklist

- Use **[canvas-checklist.md](canvas-checklist.md)** como **resumo visual** (canvas) e **checklist para a vida** (perguntas que o arquiteto pode usar em qualquer sistema).
- **Frases para fechar** (escolha uma ou duas):
  - *"Arquitetura não é sobre acertar tudo. É sobre tomar decisões melhores, com mais consciência, ao longo do tempo."*
  - *"Você não sai daqui com respostas prontas. Você sai com critérios para decidir."*
  - *"Arquitetura não é sobre acertar sempre. É sobre errar melhor, mais cedo e com menos impacto."*
  - *"Bons arquitetos não preveem o futuro. Criam sistemas que conseguem evoluir."*

---

## Sugestão de ordem em sala (com foco didático)

| Etapa | Conteúdo | O que fazer (didático) | Tempo |
|-------|----------|-------------------------|-------|
| 1 | Abertura: arquitetura como trajetória | Perguntar: “Alguém já viu projeto que parou para ‘fazer a arquitetura certa’ e atrasou?”. Introduzir ideia de trajetória vs estado final. | 10 min |
| 2 | Revisão rápida das aulas | Para cada tema (comunicação, observabilidade, SRE, performance, custo, segurança, padrões), uma frase: “Como isso se conecta à ideia de jornada?”. | 15 min |
| 3 | Conceitos centrais | Focar: contexto (variáveis que moldam decisão), monólito bem projetado, sinais para evoluir, roadmap como estratégia, trade-offs explícitos, anti-patterns. Usar exemplos concretos. | 25 min |
| 4 | Apresentação do exercício | Ler cenário; reforçar regras (não big rewrite, não copiar big tech); pedir as 2 perguntas rápidas (maior risco; o que NÃO fazer agora) antes de abrir o template. | 10 min |
| 5 | Exercício (roadmap) | Grupos ou individual preenchem template. Professor circula e faz perguntas: “Por que esse risco é o top 1?”, “O que você está abrindo mão ao adiar X?”. | 40–50 min |
| 6 | Discussão de 2–3 roadmaps | Um grupo apresenta diagnóstico; outro “o que não fazer” e trade-offs. Comparar entre grupos e com princípios do conceitos.md. | 20 min |
| 7 | Canvas + Checklist + frases de fechamento | Mostrar canvas como resumo; checklist como “levar para a vida”. Fechar com uma das frases recomendadas. | 10 min |

Ajuste os tempos conforme a carga horária.

---

## Perguntas sugeridas para cada bloco de conceitos

Use estas perguntas para **discutir** em vez de só expor:

- **Trajetória vs estado:** “O que mudaria no nosso roadmap se nosso time dobrasse em 6 meses?”
- **Contexto:** “Qual variável do cenário do exercício mais impacta suas decisões: crescimento, time ou regulatório?”
- **Monólito:** “Por que um monólito bem modularizado pode ser melhor que microsserviços mal desenhados para um time pequeno?”
- **Momento de evoluir:** “Que sinal você usaria para dizer ‘agora faz sentido extrair esse módulo’?”
- **Observabilidade:** “Por que evoluir (ex.: extrair serviço) sem observabilidade é arriscado?”
- **Roadmap:** “Qual a diferença entre ‘lista de tecnologias’ e ‘roadmap técnico’?”
- **Trade-offs:** “Dê um exemplo de trade-off que você colocaria no seu roadmap e por que explicitar isso importa.”

---

## Checklist técnico do professor (ao final da aula)

Verifique se o aluno:

- [ ] Entende arquitetura como **sequência de decisões** sob restrições, não como “estado final”?
- [ ] Consegue citar **sinais** técnicos reais para evoluir (e o que NÃO fazer por hype/medo)?
- [ ] Relaciona **observabilidade** como pré-condição para evolução segura?
- [ ] Diferencia **roadmap** (estratégia, capacidades, riscos) de “lista de tecnologias”?
- [ ] Explicita **trade-offs** nas decisões (o que estamos abrindo mão)?
- [ ] Identifica **anti-patterns** (big rewrite, copiar big tech, modismo, roadmap rígido)?
- [ ] Entende o **papel do arquiteto** como facilitador de decisões e criador de contexto?

---

## Resultado esperado (nível sênior)

O aluno deve:

- Ter **critérios** para decidir quando e como evoluir a arquitetura.
- Saber **construir um roadmap** com diagnóstico, fases, riscos, capacidades e critérios de revisão.
- **Evitar** overengineering e decisões baseadas em modismo ou medo.
- **Pensar** arquitetura como jornada contínua, com revisão e aprendizado.

**Se ele sair dizendo:** *"Agora sei como pensar arquitetura ao longo do tempo."*  
→ A Aula 12 cumpriu seu papel e a trilha se encerra com o resultado esperado.
