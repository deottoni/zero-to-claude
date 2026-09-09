# Zero to Claude — Framework de Configuração
por [Andre Ottoni](https://andreottoni.com)

---

## O que é isto

Uma configuração guiada que dá ao Claude um quadro completo de quem você é — ou de quem é o seu negócio — antes da sua primeira conversa de verdade. Ao final, o Claude conhece seu histórico, objetivos, estilo de trabalho e o trabalho específico que você faz, então você nunca mais precisa se reapresentar.

Tudo que você precisa está nesta pasta. Não existe um app separado, um painel de progresso, ou uma página para deixar aberta — você abre esta pasta no Claude, e o Claude conduz tudo de forma conversacional a partir do `CLAUDE.md`, do início ao fim. Leva cerca de 30-45 minutos.

Existem duas trilhas:

- **Profissional Autônomo (Solo)** — você é um profissional independente. Você recebe um perfil pessoal ("cérebro"), agentes e skills construídos em torno do seu trabalho real, e templates para o que você mais produz.
- **Pequena Empresa (PME)** — isto é para um time ou pequena empresa. Você recebe a mesma ideia, com escopo no negócio: um perfil de empresa compartilhado, além de agentes construídos em torno das funções específicas (vendas, operações, marketing, RH, etc.) onde você disse que a IA poderia mais ajudar.

Você não precisa escolher a trilha sozinho(a) — o Claude pergunta no início e conduz o resto a partir daí.

---

## Como rodar

1. Coloque esta pasta na sua máquina — clone este repositório, ou baixe como um ZIP e descompacte.
2. Abra na superfície do Claude que você usa:
   - **Claude Code** — abra a pasta no seu terminal (`claude /caminho/para/zero-to-claude`)
   - **Cowork** — abra a pasta como um workspace
   - **claude.ai** (navegador ou app) — crie um novo Projeto, cole todo o conteúdo do `CLAUDE.md` nas Instruções do Projeto, e envie tudo que está em `/prompts` e `/tracks` como conhecimento do Projeto
3. Diga "oi" ou "vamos lá". O Claude lê o `CLAUDE.md`, faz uma pergunta rápida (qual trilha), descobre sozinho se consegue salvar arquivos neste ambiente, e conduz o resto da configuração com você.

Só isso. O Claude acompanha sozinho em que ponto do processo você está — não há nada para marcar em nenhum outro lugar.

**Se você está no Claude Code ou Cowork**, o Claude escreve seu perfil, agentes, skills e templates diretamente nesta pasta conforme avança. **Se você está no claude.ai**, o Claude te dá textos bem identificados para você copiar nas Instruções ou no conhecimento do seu Projeto — mesmo resultado, só sem arquivos locais.

---

## Opcional: prévia visual

O `index.html` na raiz do repositório (uma pasta acima desta) é uma prévia curta do que a configuração cobre e do que você leva ao final — é a mesma página para os dois idiomas, com um alternador 🇺🇸/🇧🇷 no canto. É totalmente opcional — você nunca precisa abri-lo para de fato fazer a configuração, e ele não acompanha seu progresso. O Claude faz isso na conversa.

---

## O que tem nesta pasta

| Arquivo/Pasta | O que é |
|-------------|------------|
| `CLAUDE.md` | O arquivo mestre — o Claude lê isso primeiro, faz sua pergunta inicial, e direciona para a trilha certa |
| `tracks/solopreneur.md` | O fluxo completo para um profissional independente |
| `tracks/smb.md` | O fluxo completo para um time / pequena empresa |
| `prompts/` | Os 3-4 roteiros de coleta de contexto usados pelas duas trilhas |
| `templates/` | Gerado após a configuração — pontos de partida para suas entregas mais comuns |
| `.claude/agents/` | Agentes gerados — só Claude Code / Cowork |
| `.claude/skills/` | Skills geradas — só Claude Code / Cowork |

Depois da configuração, você vai ter uma pasta `my-brain/` (Profissional Autônomo) ou `company-brain/` (Pequena Empresa) com seus arquivos de perfil. Esse é o seu cérebro de IA — guarde com cuidado e use como seu projeto daqui para frente.

---

## Dúvidas?
[andreottoni.com](https://andreottoni.com)
