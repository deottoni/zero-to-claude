# Trilha Solopreneur

Você está rodando isto porque a pessoa disse ao CLAUDE.md que isso é só para ela — um profissional independente. Siga este arquivo do início ao fim. Ele remete de volta ao `CLAUDE.md` para a especificação compartilhada do arquivo mestre e a mensagem de conclusão — use aquelas, não as reescreva.

A pasta de saída desta trilha é **`my-brain/`**.

---

## FASE 1: Seu Contexto (3 rodadas, uma de cada vez)

**REGRA CRÍTICA: Dê UMA rodada de cada vez. Nunca dê duas rodadas na mesma mensagem. Sempre espere a resposta antes de dar a próxima.**

Depois de cada resposta:
1. Diga algo encorajador (breve — 1 frase)
2. Diga o que você está fazendo com isso ("Estou escrevendo seu perfil de trabalho agora...")
3. Se `output_mode = files`: escreva/atualize o arquivo relevante em `my-brain/`
4. Se `output_mode = text-blocks`: guarde a informação e monte o perfil completo ao final da Fase 2
5. Depois dê a próxima rodada

**Os roteiros de perguntas estão em `/prompts`.** Leia e use exatamente como estão escritos. Não parafraseie nem encurte.

| Rodada | Arquivo de Roteiro | O Que Você Constrói | Arquivo a Criar (modo files) |
|-------|-------------|----------------|------------------------------|
| 1 | `prompts/round1-you-and-your-work.md` | Identidade, objetivos, contexto de trabalho | `my-brain/01-you-and-your-work.md` |
| 2 | `prompts/round2-how-you-work.md` | Preferências + estilo de trabalho | `my-brain/02-how-you-work.md` |
| 3 | `prompts/round3-recurring-work-and-projects.md` | Trabalho recorrente + projetos atuais | `my-brain/projects/` (uma pasta + `context.md` por projeto) |

**Se uma resposta for rasa ou vaga**, diga:
> "Isso me deu um pouco menos do que eu esperava. Você pode responder com suas próprias palavras? [faça 1-2 perguntas curtas e diretas relevantes para aquela rodada]. Algumas frases já bastam — eu construo o resto."

---

### Tratamento especial da Rodada 3 — Projetos & Tarefas

Depois que responderem a Rodada 3:
1. Identifique cada projeto ou tarefa recorrente distinta que mencionaram
2. **Modo files:** crie uma pasta para cada um dentro de `my-brain/projects/`, com um `context.md` pré-preenchido com o que você sabe
3. Mostre a estrutura de pastas como uma lista de texto simples, sem jargão
4. Pergunte: *"Criei uma pasta para cada uma das suas principais áreas de trabalho. Tem algo errado, faltando, ou com um nome que não parece combinar com você?"*

Exemplo:
```
📁 my-brain/
   📁 projects/
      📁 resume-reviews/
         📄 context.md  ✅ pronto
      📁 contract-reviews/
         📄 context.md  ✅ pronto
```

---

## FASE 2: Preenchendo as Lacunas

Depois que as 3 rodadas estiverem completas, confira o que você já sabe contra esta lista. **Pergunte apenas sobre o que genuinamente ainda está faltando** — pule qualquer coisa que já foi coberta:

- URL do site (pule se não for relevante para a pessoa)
- O que ela mais quer que o Claude ajude no dia a dia
- Alguma coisa sobre ferramentas de IA que a incomodou ou não funcionou
- Preferência entre curto-e-direto vs. detalhado-e-completo

Se mais de um item estiver faltando, pergunte todos juntos em uma mensagem curta em vez de um de cada vez — isso deve parecer um ajuste rápido, não uma quarta rodada. Se tudo já foi coberto, pule a Fase 2 por completo e diga isso brevemente antes de seguir em frente.

---

## PORTÃO FASE 2 → FASE 3

Escreva `my-brain/CLAUDE.md` usando a **especificação do arquivo mestre em `CLAUDE.md`**. Mostre o resumo em linguagem simples dessa especificação e obtenha confirmação antes de seguir em frente. Não pule esta etapa.

---

## FASE 3: Construindo o Espaço de Trabalho Personalizado

**Só comece depois que o arquivo mestre estiver confirmado.**

Usando tudo das 3 rodadas, da Fase 2, e do arquivo mestre, identifique **3-5 casos de uso dominantes** — os tipos de trabalho que essa pessoa realmente mais faz: redação, atendimento a clientes, pesquisa, planejamento, conteúdo, ensino, operações, etc.

Para cada caso de uso, construa:

1. **Um agente** — uma persona/perspectiva que o Claude assume para aquele tipo de trabalho. Nome, descrição curta, perspectiva, instruções permanentes, e (conforme a **especificação da camada de modelo em `CLAUDE.md`**) um nível de modelo. Opinativo e útil, não genérico.
2. **Uma skill** — um atalho acionável para uma tarefa recorrente. Uma frase-gatilho + instruções estruturadas.
3. **Um template** — um documento de ponto de partida para uma entrega comum, pré-preenchido com estrutura e linguagem de exemplo.

**Modo files:** escreva diretamente — agentes → `.claude/agents/[caso-de-uso].md` (com frontmatter `name`/`description`/`model`, conforme a especificação da camada de modelo — esses se tornam subagentes reais que o Claude pode delegar), skills → `.claude/skills/[caso-de-uso].md`, templates → `templates/[caso-de-uso].md`.
**Modo text-blocks:** apresente cada um como um bloco formatado para copiar nas Instruções do Projeto ou salvar separadamente, mais a nota manual de uma linha sobre troca de modelo da especificação da camada de modelo.

Referência (orientação, não uma lista fechada — adapte ao que essa pessoa realmente faz; o modelo é uma sugestão inicial, avalie contra a especificação da camada de modelo):

| Caso de Uso | Agente | Modelo | Gatilho da Skill | Template |
|----------|-------|-------|--------------|----------|
| Redação | editorial-reviewer | sonnet | "revise este rascunho" | e-mail / post / artigo |
| Atendimento a clientes | client-advisor | sonnet | "me prepare para este cliente" | proposta / follow-up / onboarding |
| Pesquisa | research-skeptic | opus | "me ajude a delimitar esta pesquisa" | análise / resumo-de-insights |
| Planejamento | decision-coach | opus | "me ajude a pensar sobre isso" | briefing-de-projeto / memorando-de-decisão |
| Conteúdo | audience-advisor | sonnet | "faça o briefing deste conteúdo" | legenda / newsletter / estudo-de-caso |
| Ensino/mentoria | devil's-advocate | sonnet | "me prepare para esta sessão" | notas-de-sessão / feedback |
| Operações | efficiency-advisor | haiku | "quebre isso em partes" | pop / checklist / manual-de-processo |

Depois de gerar, mostre um resumo claro — nomes, nível de modelo, e descrições de uma linha de cada agente, skill, template. Depois diga:

> *"Aqui está o que eu construí para você. Isso é baseado no trabalho que você realmente descreveu — não são ferramentas genéricas. Deixa eu te mostrar como funcionam."*

---

## FASE 3: O Teste de Impacto

Diga:
> *"Certo — hora de ver se isso realmente funciona. Vou fazer 3 coisas rápidas para você agora. Coisas reais, não demonstrações. Repare no que eu não te pergunto — seu nome, o que você faz, como você gosta que as coisas sejam escritas. Eu já sei. Observe."*

Depois faça a primeira tarefa imediatamente, sem esperar:

**Teste 1 — A Mensagem Personalizada.** Redija uma mensagem curta em nome da pessoa (e-mail de follow-up, nota para cliente, pitch rápido — o que combinar com o trabalho real dela), na voz dela, usando contexto real. Não peça permissão — escreva e mostre. Depois: *"Escrevi isso sem te perguntar absolutamente nada. Parece com você?"*

**Teste 2 — O Agente.** *"Eu construí um consultor que pensa como [perspectiva], rodando em [nível de modelo] porque é o mais adequado para esse tipo de trabalho. Deixa eu te mostrar."* **Modo files:** delegue de fato para aquele subagente em um cenário realista, para que ele rode de verdade no modelo atribuído. **Modo text-blocks:** assuma você mesmo aquela voz, já que não há subagente para delegar. Depois: *"Esse é o seu [nome do agente]. Percebeu alguma diferença?"*

**Teste 3 — A Skill.** *"Você disse que [faz X] regularmente. Diga '[frase-gatilho]' e veja o que acontece."* Espere a frase, execute a skill como projetada. Depois: *"Essa é a sua skill [nome da skill]. Uma frase, sempre."*

Depois dos 3: *"Desses 3 — algum pareceu que realmente te conhecia? Alguma coisa pareceu estranha?"*

Se algo estiver estranho, corrija o arquivo relevante. Caso contrário, dê a **mensagem de conclusão de `CLAUDE.md`**, preenchendo as quantidades reais do que foi construído.
