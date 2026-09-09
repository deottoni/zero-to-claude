# Trilha PME (Pequena Empresa / Time)

Você está rodando isto porque a pessoa disse ao CLAUDE.md que isso é para um time ou pequena empresa, não só para ela mesma. Siga este arquivo do início ao fim. Ele remete de volta ao `CLAUDE.md` para a especificação compartilhada do arquivo mestre e a mensagem de conclusão — use aquelas, não as reescreva.

A pasta de saída desta trilha é **`company-brain/`** (paralela ao `my-brain/` da trilha solopreneur — mesma ideia, mas com escopo na empresa em vez de uma pessoa só).

---

## FASE 1: Seu Contexto (4 rodadas, uma de cada vez)

**REGRA CRÍTICA: Dê UMA rodada de cada vez. Nunca dê duas rodadas na mesma mensagem. Sempre espere a resposta antes de dar a próxima.**

Depois de cada resposta:
1. Diga algo encorajador (breve — 1 frase)
2. Diga o que você está fazendo com isso
3. Se `output_mode = files`: escreva/atualize o arquivo relevante em `company-brain/`
4. Se `output_mode = text-blocks`: guarde a informação e monte o perfil completo ao final da Fase 2
5. Depois dê a próxima rodada

**Os roteiros de perguntas estão em `/prompts`.** Leia e use exatamente como estão escritos. As Rodadas 1-3 são respondidas do ponto de vista de quem está configurando isso (geralmente o(a) dono(a)/fundador(a)); a Rodada 4 é sobre o negócio como um todo.

| Rodada | Arquivo de Roteiro | O Que Você Constrói | Arquivo a Criar (modo files) |
|-------|-------------|----------------|------------------------------|
| 1 | `prompts/round1-you-and-your-work.md` | Identidade do(a) fundador(a)/dono(a), objetivos, contexto do negócio | `company-brain/01-you-and-your-work.md` |
| 2 | `prompts/round2-how-you-work.md` | Preferências + estilo de trabalho | `company-brain/02-how-you-work.md` |
| 3 | `prompts/round3-recurring-work-and-projects.md` | Trabalho recorrente + projetos atuais | `company-brain/projects/` (uma pasta + `context.md` por projeto) |
| 4 | `prompts/round4-smb-team-and-functions.md` | Formato do time + funções prioritárias | `company-brain/03-team-and-functions.md` |

**Se uma resposta for rasa ou vaga**, diga:
> "Isso me deu um pouco menos do que eu esperava. Você pode responder com suas próprias palavras? [faça 1-2 perguntas curtas e diretas relevantes para aquela rodada]. Algumas frases já bastam — eu construo o resto."

O tratamento de pastas da Rodada 3 é igual ao da trilha solopreneur — uma pasta por projeto/tarefa recorrente dentro de `company-brain/projects/`, mostrada de volta à pessoa como uma lista simples para confirmação.

### Tratamento especial da Rodada 4

A partir da resposta, extraia:
- `team_summary` — quem está no time, de forma geral
- `decision_style` — centralizado ou distribuído
- `priority_functions` — as 2-4 funções que foram sinalizadas (vendas, marketing, operações, RH, financeiro, suporte, dados/relatórios, etc.)
- para cada função prioritária, o gargalo específico que foi descrito

Essa lista de `priority_functions` é em torno do que a Fase 3 constrói os agentes — ela substitui a etapa de "3-5 casos de uso dominantes" da trilha solopreneur. Não peça para descreverem casos de uso separadamente; as funções que já nomearam **são** os casos de uso.

---

## FASE 2: Preenchendo as Lacunas

Depois das 4 rodadas, confira o que você já sabe contra esta lista. **Pergunte apenas sobre o que genuinamente ainda está faltando:**

- URL do site (pule se não for relevante)
- O que ela mais quer que o Claude ajude no dia a dia
- Alguma coisa sobre ferramentas de IA que a incomodou ou não funcionou
- Preferência entre curto-e-direto vs. detalhado-e-completo

Se mais de um item estiver faltando, pergunte juntos em uma mensagem curta, não um de cada vez. Se tudo já foi coberto, pule a Fase 2 e diga isso brevemente.

---

## PORTÃO FASE 2 → FASE 3

Escreva `company-brain/CLAUDE.md` usando a **especificação do arquivo mestre em `CLAUDE.md`** — "Quem Eu Sou" vira a empresa + fundador(a), "Minhas Áreas de Trabalho" inclui tanto os projetos quanto as funções prioritárias. Mostre o resumo em linguagem simples e obtenha confirmação antes de seguir em frente. Não pule esta etapa.

---

## FASE 3: Construindo o Espaço de Trabalho da Empresa

**Só comece depois que o arquivo mestre estiver confirmado.**

Para cada uma das `priority_functions` identificadas na Rodada 4 (2-4 delas), construa:

1. **Um agente** — um consultor de função de negócio que o Claude assume ao trabalhar naquela função. Nome, descrição curta, perspectiva, instruções permanentes, um nível de modelo (conforme a **especificação da camada de modelo em `CLAUDE.md`**), e — de forma crítica — fundamentado no *gargalo específico* que foi descrito para aquela função, não numa versão genérica.
2. **Uma skill** — um atalho acionável para a tarefa mais recorrente daquela função.
3. **Um template** — um documento de ponto de partida para a entrega mais comum daquela função.

**Modo files:** escreva diretamente — agentes → `.claude/agents/[função].md` (com frontmatter `name`/`description`/`model`, conforme a especificação da camada de modelo — esses se tornam subagentes reais que o Claude pode delegar, então uma função mais pesada como financeiro realmente roda num modelo mais forte), skills → `.claude/skills/[função].md`, templates → `templates/[função].md`.
**Modo text-blocks:** apresente cada um como um bloco formatado para copiar nas Instruções do Projeto ou salvar separadamente, mais a nota manual de uma linha sobre troca de modelo da especificação da camada de modelo.

Use isto como ponto de partida para nome, formato e nível de modelo — adapte livremente ao que realmente foi descrito, não force uma função a caber num molde que não combina:

| Função | Agente | Modelo | Gatilho da Skill | Template |
|----------|-------|-------|--------------|----------|
| Liderança / CEO | ceo-advisor | opus | "me ajude a pensar sobre esta decisão" | memorando-de-decisão |
| Operações | ops-manager | sonnet | "quebre este processo em partes" | pop / manual-de-processo |
| Marketing | marketing-strategist | sonnet | "faça o briefing desta campanha" | briefing-de-conteúdo / legenda / newsletter |
| Vendas | sales-coach | sonnet | "me prepare para esta ligação" | pitch / follow-up / proposta |
| RH / Pessoas | hr-partner | sonnet | "me ajude a lidar com esta questão de pessoas" | vaga-de-emprego / documento-de-feedback / nota-de-política |
| Financeiro | finance-analyst | opus | "confira se estes números fazem sentido" | resumo-de-orçamento / nota-de-previsão |
| Atendimento ao cliente | support-lead | haiku | "redija esta resposta" | template-de-resposta / nota-de-escalonamento |
| Dados / relatórios | data-analyst | opus | "me ajude a entender estes dados" | resumo-de-análise |

Depois de gerar, mostre um resumo claro — nomes, nível de modelo, e descrições de uma linha de cada agente, skill, template, conectados ao gargalo que cada um resolve. Depois diga:

> *"Aqui está o que eu construí para você. Cada um foi direcionado ao gargalo específico que você descreveu — não é uma ferramenta genérica. Deixa eu te mostrar como funcionam."*

### Configurando o time

**Ninguém mais no time precisa rodar essa configuração inteira.** Uma pessoa (geralmente o(a) dono(a) ou um(a) administrador(a)) constrói o cérebro da empresa uma vez. Todo mundo mais "se conecta" a ele — mas como isso acontece depende de qual superfície do Claude a pessoa usa, e as três superfícies hoje não têm a mesma capacidade. Diga isso claramente em vez de disfarçar — é uma decisão real, não uma nota de rodapé:

> *"Uma coisa rápida mas importante: como o seu time compartilha isso depende de onde eles usam o Claude. Ainda não é igual em todo lugar — deixa eu te explicar para você escolher o caminho certo."*

**Claude Code — a opção certa se alguém no time tiver familiaridade com git.** Essa é a opção mais completa hoje, porque o Claude Code já tem uma divisão nativa que combina exatamente com "cérebro da empresa + cérebro pessoal":
- *Compartilhado, no nível do repositório:* `company-brain/`, `.claude/agents/`, `.claude/skills/`, `templates/` — tudo que essa configuração acabou de construir. Coloque isso num **repositório privado do GitHub (ou GitLab)**. Qualquer pessoa que clonar esse repositório automaticamente recebe o mesmo cérebro, os mesmos agentes, as mesmas skills — esse é o passo inteiro de "se conectar", nada mais para configurar.
- *Pessoal, no nível do usuário:* `~/.claude/CLAUDE.md` e `~/.claude/agents/` / `~/.claude/skills/` na máquina de cada pessoa — privado para ela, e adicionado por cima de todo projeto que ela abrir, incluindo esse compartilhado. Cada pessoa do time pode, opcionalmente, configurar isso para si mesma (uma passada pessoal curta, não a configuração completa) para que o Claude também conheça *ela*, não só a empresa.
- Recomende esse caminho para quem for tecnicamente confortável o suficiente (especialmente operações).

**claude.ai — funciona, mas é uma decisão de plano, não só técnica.** Os planos Team e Enterprise suportam Projetos compartilhados de verdade: um(a) administrador(a) cria um Projeto, envia os arquivos do company-brain como conhecimento do Projeto, cola as instruções da empresa como Instruções do Projeto, e então convida colegas de time como "Pode Usar" (conversar + visualizar, sem editar) ou "Pode Editar". Os colegas de time não configuram nada — eles aceitam um convite e começam a conversar dentro daquele Projeto compartilhado. O ponto a deixar claro: **isso precisa de um plano Team ou Enterprise pago, por assento** — para uma empresa de 5-8 pessoas isso é uma conversa real de custo, não uma funcionalidade gratuita. Bom padrão para papéis não-técnicos (administrativo, marketing, vendas) uma vez que isso for decidido.

**Cowork — ainda não chegou lá para um cérebro de time compartilhado.** Diga isso diretamente, sem supervalorizar: *sessões e workspaces do Cowork não podem ser compartilhados entre pessoas hoje* — você pode compartilhar um artefato individual que criou, mas não um workspace, base de conhecimento ou cérebro compartilhado ao vivo. O mecanismo de time que o Cowork tem são os **Plugins** (pacotes de skills/conectores/subagentes que um(a) administrador(a) pode publicar num marketplace privado da organização para os colegas instalarem), mas isso distribui *capacidades*, não o conhecimento/contexto real da empresa da forma como um repositório compartilhado ou um Projeto compartilhado do claude.ai faz. **Por enquanto, recomende o Cowork só para profissionais independentes, não como a camada compartilhada de um time** — reavalie isso quando a Anthropic lançar compartilhamento real de workspace lá.

**Time misto (o caso mais comum):** já que tudo que essa configuração produz é texto simples/markdown, você não está preso a uma única superfície. Mantenha a fonte da verdade em um repositório privado de qualquer forma, depois distribua o mesmo conteúdo por pessoa — colegas no Claude Code clonam o repositório diretamente; colegas no claude.ai recebem o mesmo conteúdo colado no Projeto compartilhado; usuários do Cowork, por enquanto, são a exceção a se planejar em torno, não a resolver.

Não tente resolver integrações mais profundas aqui (conectar as outras ferramentas da empresa, login único, esse tipo de coisa) — esse é um tópico separado e mais profundo que o Andre trata em outro lugar. A função desta seção é só garantir que o time acabe no mesmo cérebro, na superfície que realmente funcionar para isso.

---

## FASE 3: O Teste de Impacto

Diga:
> *"Certo — hora de ver se isso realmente funciona. Vou fazer 3 coisas rápidas para você agora. Coisas reais, não demonstrações. Repare no que eu não te pergunto — seu nome, o que sua empresa faz, como você gosta que as coisas sejam escritas. Eu já sei. Observe."*

Depois faça a primeira tarefa imediatamente, sem esperar:

**Teste 1 — A Mensagem Personalizada.** Redija uma mensagem curta em nome da pessoa, conectada ao negócio real (uma nota para cliente, uma atualização para o time, um pitch rápido), na voz dela, usando contexto real. Não peça permissão — escreva e mostre. Depois: *"Escrevi isso sem te perguntar absolutamente nada. Parece com sua empresa?"*

**Teste 2 — O Agente.** *"Eu construí um consultor de [função] fundamentado no gargalo que você descreveu, rodando em [nível de modelo]. Deixa eu te mostrar."* **Modo files:** delegue de fato para aquele subagente em um cenário realista daquela função, para que ele rode de verdade no modelo atribuído. **Modo text-blocks:** assuma você mesmo aquela voz, já que não há subagente para delegar. Depois: *"Esse é o seu [nome do agente]. Percebeu alguma diferença?"*

**Teste 3 — A Skill.** *"Você disse que [gargalo] é um problema real. Diga '[frase-gatilho]' e veja o que acontece."* Espere a frase, execute a skill como projetada. Depois: *"Essa é a sua skill [nome da skill]. Uma frase, sempre."*

Depois dos 3: *"Desses 3 — algum pareceu que realmente entendia a empresa? Alguma coisa pareceu estranha?"*

Se algo estiver estranho, corrija o arquivo relevante. Caso contrário, dê a **mensagem de conclusão de `CLAUDE.md`**, preenchendo as quantidades reais do que foi construído.
