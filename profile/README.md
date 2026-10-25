<p align="center">
  <img src="https://raw.githubusercontent.com/Brasil-Imposto/.github/main/profile/images/logo.png" width="120" alt="Marca do Brasil-Imposto">
</p>

<h1 align="center">Brasil·Imposto</h1>

<p align="center">
  <b>Para onde vai o imposto, com dados oficiais e a fonte de cada número.</b><br>
  Um projeto cívico, apartidário e de código aberto. Qualquer pessoa pode contribuir.
</p>

<p align="center">
  <a href="https://brasil-imposto.github.io"><b>Site</b></a> ·
  <a href="https://github.com/Brasil-Imposto/brasil-imposto.github.io">Código e documentação</a> ·
  <a href="https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new/choose">Abrir uma issue</a> ·
  <a href="https://github.com/Brasil-Imposto/brasil-imposto.github.io/discussions">Discussions</a> ·
  <a href="#in-english">English</a>
</p>

<p align="center">
  <a href="https://brasil-imposto.github.io"><img src="https://raw.githubusercontent.com/Brasil-Imposto/.github/main/profile/images/inicio-1440.png" width="720" alt="O site: o mapa do Brasil com o saldo de cada estado com a União"></a>
</p>

Esta página reúne as regras para contribuir com o Brasil-Imposto: como começar, como virar colaborador e como preparar e
documentar um pull request. A documentação do projeto (o que cada página mostra, de onde vem cada número e como rodar na sua
máquina) está no [README do repositório](https://github.com/Brasil-Imposto/brasil-imposto.github.io#readme).

## O caminho de uma contribuição

1. **Uma issue primeiro.** Abra pelo formulário que combina com o que você quer fazer, ou escolha uma
   [issue aberta](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues) e comente que vai assumir. Antes, veja se a
   tarefa já tem dono: uma issue, um pull request ou um ramo abertos sobre ela. Se tiver, comente lá em vez de começar outra.
2. **Um pull request para o ramo `staging`**, nunca para a `main`, com a mudança documentada como diz a seção "O que todo pull
   request leva".
3. **As checagens automáticas** (`ci` e `dco`) rodam e precisam passar.
4. **A revisão:** o mantenedor lê, pede ajustes se for preciso e aprova. O merge no `staging` é por squash.
5. **O site de testes:** o `staging` vai ao ar em <https://brasil-imposto.github.io/staging/> (hoje pelo mantenedor, a cada lote
   de merges; automático quando o deploy for ligado), onde a mudança é conferida como vai ficar.
6. **A produção, só depois disso:** quando a mudança está bem no staging, o mantenedor a leva para a `main`, que publica
   <https://brasil-imposto.github.io>, uma tarefa aprovada por vez, nunca o `staging` inteiro. Uma funcionalidade nova vai com a sua chave desligada na produção, e só aparece ali quando o
   mantenedor liga essa chave.

## Antes de começar

- Leia o [README do repositório](https://github.com/Brasil-Imposto/brasil-imposto.github.io#readme), as
  [regras de neutralidade](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/GOVERNANCE.md) e o
  [código de conduta](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/CODE_OF_CONDUCT.md).
- Veja as [decisões do projeto](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/docs/decisions/README.md):
  muita pergunta já tem resposta ali, com o motivo.
- Falhas de segurança não vão em issue aberta: siga a
  [política de segurança](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/SECURITY.md).

## Como virar colaborador

Não é preciso pedir permissão: qualquer pessoa com uma conta no GitHub pode abrir issues e pull requests. Os formulários de issue
cobrem os casos mais comuns:

| Formulário | Para |
|---|---|
| [Pedir correção](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=data-correction.yml) | Um número errado, com o link da fonte oficial com o valor certo |
| [Acrescentar uma fonte](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=add-source.yml) | Uma base oficial que o projeto ainda não usa |
| [Cobrir os municípios de um estado](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=new-state.yml) | Levar ao seu estado o que SC e RS já têm |
| [Propor um caso](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=new-case.yml) | Uma obra ou um gasto com documentos oficiais |
| [Propor uma mudança de método](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=method-proposal.yml) | Uma regra de cálculo que deveria mudar |
| [Relatar um defeito](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new?template=bug-report.yml) | Algo que não funciona no site |

Quem contribui com frequência passa a revisar: pelas fases da
[governança](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/GOVERNANCE.md), três pessoas contribuindo com
frequência (por exemplo, cinco pull requests aceitos em três meses) formam o time de revisores, com o papel Triage e depois Write.
A governança diz também como o projeto chega a um segundo mantenedor e a um conselho.

## Como preparar um pull request

1. **Faça um fork** do repositório e crie um ramo a partir do `staging`, com o tipo e o assunto em inglês: `fix/map-legend`,
   `feat/senate-september-quota`, `docs/pipeline-guides`.
2. **Um assunto por pull request.** Duas mudanças independentes são dois pull requests.
3. **Assine cada commit** com `git commit -s` (Developer Certificate of Origin). O check `dco` recusa commit sem assinatura.
4. **Mensagens de commit e o título do pull request em inglês**, no formato `type(area): what changes` (o título vira a
   mensagem do commit no merge). Tipos: `feat`, `fix`, `docs`, `refactor`, `test`, `ci`, `build`. Exemplos:
   `fix(site): map legend on phones`, `feat(data): Senate quota for September 2026`. A descrição do pull request pode ser em
   português ou em inglês.
5. **Uma funcionalidade nova que aparece na tela vem com a sua chave** em `data/features.json`: `key` em inglês, `issue` com o
   número da issue, `staging: true` e `production: false`. Desligada, ela não entra na página da produção (nem marcação, nem
   estilo, nem script); nunca é só escondida. Uma correção não precisa de chave.
6. **Abra o pull request** para o `staging` (o ramo padrão do repositório). O formulário do pull request já vem com as seções da
   próxima parte: preencha todas.

## O que todo pull request leva

Um pull request bem documentado deixa qualquer pessoa entender o que mudou sem abrir o código. Todo pull request tem:

| Seção | O que escrever |
|---|---|
| **Título** | `type(area): what changes`, em inglês e em uma linha |
| **O que muda e por quê** | O problema, a mudança e o motivo, em frases curtas |
| **Issue relacionada** | `Closes #123`, ou o link da discussão que levou à mudança |
| **Capturas de tela** | Para toda mudança que aparece na tela: antes e depois, no computador (1440 px de largura) e no celular (420 px) |
| **Fontes** | Para todo número novo ou mudado: o órgão, o link, o período de referência e a data em que a fonte foi lida |
| **Como foi conferido** | Os comandos rodados e a saída de cada um: os testes, a checagem ao centavo e o erro plantado que a checagem pegou |
| **Lista de conferência** | A lista do formulário, marcada; um item não marcado leva uma linha dizendo por quê |

Um exemplo, resumido:

```markdown
fix(site): keep the sheet's close button above the header

## O que muda e por quê
O cabeçalho cobria o topo da ficha de cada pessoa em Os 3 Poderes, e o botão Fechar não podia ser clicado.
A ficha passa a ficar acima do cabeçalho, como em qualquer janela.

## Issue relacionada
Closes #57

## Capturas de tela
| | Antes | Depois |
|---|---|---|
| 1440 px | (imagem) | (imagem) |
| 420 px | (imagem) | (imagem) |

## Como foi conferido
- `uv run python -m unittest discover -s pipelines/tests`: 31 testes, todos passam
- sonda do botão Fechar: o elemento no centro do botão é o próprio botão, nas 7 larguras
- controle: com a regra antiga, a sonda falha nas 7 larguras
```

## As regras que valem em toda mudança

**Dados**

- Nenhum número sem fonte oficial, com link, período de referência e data da coleta. Sem fonte, não aparece.
- O script em `pipelines/` ou `docs/superpowers/tools/` refaz o arquivo sozinho, a partir da fonte; ninguém edita dado à mão.
- Todo total bate com o total oficial da fonte, ao centavo, e toda soma da tela fecha à mão com os valores como aparecem.
- O que a fonte não põe em nenhum estado fica em "sem informação de estado". Uma estimativa só entra se a decisão do projeto
  permitir, e a tela diz que é estimativa.
- Um item que o projeto não tem aparece como "não publicado".

**Texto**

- Neutro: o site mostra dados e mecanismos, nunca pede voto nem julga. Um estado "envia mais do que recebe" ou "recebe mais do
  que envia".
- Pessoas aparecem só com o papel que têm num documento oficial, com o ato e o link.
- Qualquer governo e qualquer partido têm o mesmo tratamento.
- Quando os números não fecham, a tela diz "diferença sem explicação"; nunca "desvio" sem uma decisão oficial.

**Código**

- Identificadores, nomes de arquivo, chaves de JSON e mensagens de commit em inglês; o texto da tela e a documentação em português.
- Toda checagem nova vem com um controle: um erro plantado que a checagem precisa pegar.
- Uma mudança grande começa por uma proposta (o formulário "Propor uma mudança de método", ou uma discussão) antes do código.
- Uma página mudada é aberta em 1440 e 420 px de largura antes do pull request.

## Revisão e merge

- **Checagens obrigatórias:** `ci` (testes, os construtores das páginas e o site em Astro) e `dco` (a assinatura dos commits). Com
  uma delas vermelha, o pull request não entra.
- **Revisão:** hoje o mantenedor revisa todo pull request, inclusive os próprios: tudo entra por pull request, sem exceção. Ele
  pode pedir ajustes; responda no próprio pull request e envie novos commits no mesmo ramo.
- **Merge:** no `staging`, por squash, com o título do pull request como mensagem, e só com o ok do mantenedor.
- **Site de testes:** o `staging` é publicado em <https://brasil-imposto.github.io/staging/> (hoje pelo mantenedor, a cada lote de
  merges; automático quando o deploy for ligado), com a faixa "Ambiente de testes"
  e fora dos buscadores. Ali o mantenedor e quem contribuiu conferem a mudança antes de qualquer passo para a produção.
- **Produção:** a `main` publica <https://brasil-imposto.github.io> e recebe uma tarefa aprovada por vez: para cada uma, um
  pull request do mantenedor com só os commits dela, depois de conferida no site de testes; o que não foi aprovado fica no
  `staging`. Logo depois, a `main` volta para o `staging` (back-merge), para os dois ramos não se afastarem. O site é conferido no ar depois do deploy.
- **Correção urgente:** só o mantenedor, num ramo `hotfix/*` saído da `main`; a correção volta em seguida para o `staging`.

## Onde falar

- Dúvidas, ideias e propostas: [Discussions](https://github.com/Brasil-Imposto/brasil-imposto.github.io/discussions).
- Um número errado ou um defeito: um dos [formulários de issue](https://github.com/Brasil-Imposto/brasil-imposto.github.io/issues/new/choose).
- Segurança, em privado: a [política de segurança](https://github.com/Brasil-Imposto/brasil-imposto.github.io/blob/main/SECURITY.md).

Código: AGPL-3.0. Dados e textos: CC BY 4.0.

## In English

Brasil-Imposto is a civic, nonpartisan, open-source map of Brazilian public money built only from official data. Anyone can
contribute: check that nobody has the task yet (an open issue, pull request or branch for it), open an issue through one of the forms, then a pull request to `staging` from a fork (branch from `staging`, never
`main`), one subject per pull request, every commit signed off (`git commit -s`). Every pull request carries a `type(area): what changes` title in English, what changes and why, the
related issue, before and after screenshots at 1440 and 420 px for any visible change, the official source of every new number,
and the checks that were run with their output. The `ci` and `dco` checks must pass; the maintainer reviews and merges by squash into
`staging`, which publishes the test site <https://brasil-imposto.github.io/staging/>. Production (`main`) only receives the
maintainer's promotion of `staging`, after the change was checked there, and a new feature ships behind its switch in
`data/features.json`, off in production until the maintainer turns it on. Issues and pull requests are welcome in Portuguese or English. Project documentation:
<https://github.com/Brasil-Imposto/brasil-imposto.github.io#readme>.
