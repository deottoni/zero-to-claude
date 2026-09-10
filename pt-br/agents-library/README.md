# agents-library/

Modelos de partida para os 8 agentes de função de negócio da trilha PME — não são genéricos de
preenchimento, são as mesmas 8 funções e níveis de modelo já nomeados na tabela de referência de
`../tracks/smb.md` (Liderança, Operações, Marketing, Vendas, RH, Financeiro, Atendimento, Dados).

**Como isso é usado durante o onboarding:** quando a trilha PME identifica uma função prioritária,
Claude copia o arquivo correspondente daqui pra `.claude/agents/[função].md`, e então **adapta**
— incorpora o gargalo específico que a pessoa descreveu, o contexto real do negócio dela, os nomes
do time se for relevante — em vez de gerar um agente do zero. A persona, o escopo e as instruções
de cada arquivo aqui são um ponto de partida sólido e opinativo; o passo de adaptação é o que faz
o resultado parecer construído pra *esse* negócio, não copiado e colado.

Cada arquivo é um front matter mínimo e real de `.claude/agents/*.md` (`name`/`description`/`model`)
mais uma persona, uma linha de escopo (pra que serve e pra que não serve), uma lista curta de "como
você trabalha", e 2-3 exemplos de uso — deliberadamente não as listas enormes de capacidade,
ferramenta por ferramenta, que você encontra em grandes coleções open-source de subagentes. Isso é
pra times pequenos, não pra empresas grandes: o dono de uma PME precisa de um agente que dê ajuda
boa e específica rápido, não um que cite uma stack de BI que ele nunca vai usar.
