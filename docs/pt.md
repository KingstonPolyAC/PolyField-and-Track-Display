---
title: PolyField & Track Display — Manual
description: Ajuda e manual do utilizador do PolyField & Track Display — software de visualização e apresentação de resultados para os sistemas de photo-finish FinishLynx e TimeTronics.
lang: pt
permalink: /pt/
---

# PolyField & Track Display

Um software de visualização e apresentação de resultados para os sistemas de photo-finish FinishLynx e TimeTronics. Funciona em Windows e Mac como uma aplicação de secretária ligada à pasta de resultados do seu photo-finish.

[Descarregar em polyfield.co.uk](https://www.polyfield.co.uk)

* Índice
{:toc}

## Descrição geral

O PolyField & Track Display transforma os resultados do seu FinishLynx ou TimeTronics em ecrãs ao vivo por todo o recinto. Uma única instância de secretária monitoriza a pasta de resultados e serve uma interface web que qualquer dispositivo na rede pode abrir — quadros de resultados, um quiosque de autoatendimento para atletas, um quadro de velocidade e muito mais.

Mantém o **operador no controlo**: os resultados só aparecem depois de guardados, garantindo uma validação positiva antes da apresentação. São suportadas várias gravações — pode mostrar cedo os atletas de provas de fundo, ou revelar uma corrida assim que os 3 primeiros tiverem marcas atribuídas.

## Como funciona

- Executa **uma instância** da aplicação de secretária num computador ligado à pasta de resultados do photo-finish.
- A aplicação cria uma interface web na **porta 3000**. Qualquer dispositivo na mesma rede abre-a num browser — sem necessidade de instalação nos ecrãs.
- Cada ecrã regista-se e pode receber um esquema para mostrar. O número de ecrãs é limitado apenas pela sua rede e pelo computador anfitrião.
- O operador controla o que aparece — resultados, sobreposições (texto, proteção de ecrã, contagem decrescente, recordes, vista de linha) ou um esquema personalizado completo.

## Primeiros passos

### 1. Definir a pasta de resultados

Esta é a pasta onde o FinishLynx ou o TimeTronics guarda os resultados (LIF, etc.). Clique no botão vermelho no canto superior direito, **«Select Results Folder»**. Pode alterá-la mais tarde com **«Change Folder»**.

![Defina a pasta de resultados ou modifique o caminho no canto superior direito:](assets/desktop.png)

Uma vez definida, a interface web é criada e o endereço de acesso é mostrado no topo da aplicação de secretária (p. ex. `http://display.local:3000` ou `http://<o-seu-IP>:3000`).

### 2. Abrir um ecrã

Em cada dispositivo de ecrã, abra um browser e vá ao endereço mostrado, seguido de `/display`. Cada ecrã que se liga recebe automaticamente um número. Consulte [Ligar ecrãs](#connecting-screens) para o atalho por código QR.

> **Dica** — deixe a aplicação de secretária no ecrã inicial e controle os ecrãs a partir daí, ou de um segundo dispositivo na interface web. Assim mantém o controlo das sobreposições enquanto os resultados fluem automaticamente.

## O painel de controlo de secretária

O painel de controlo é a base do operador. No topo define a pasta de resultados e vê o endereço de ligação. Os controlos principais estão agrupados numa fila compacta de botões (que passa a uma segunda fila em janelas estreitas):

| Controlo | O que faz |
|---|---|
| **Text & screensaver** | Escreva uma mensagem para mostrar em todos os ecrãs, ou associe um gráfico. Ótimo para mensagens de patrocinadores, «prova suspensa», etc. |
| **Screensaver** | Mostra uma **imagem** associada ou um **esquema guardado** à escolha na área de proteção de ecrã. Se já houver uma fonte definida, um toque ativa/desativa; o botão ⚙ reabre as opções. |
| **Line View** | Envia a imagem de photo-finish mais recente para os ecrãs. Desativado até surgirem JPGs de photo-finish na pasta de resultados. |
| **Clock** | Mostra o relógio em curso em ecrã inteiro nos ecrãs com um widget de relógio. |
| **Testar / Pódio / Seleção manual** | Surgem quando um esquema usa momentos: reproduz um cartão de exemplo em todos os ecrãs, mostra o pódio do resultado atual ou envia um recorde à escolha. Ver [Momentos](#moments). |
| **Countdown** | Conta de forma decrescente até uma hora-alvo. Introduza a hora e Iniciar; oculta-se ao chegar a zero. |
| **Layout Builder** | Abre o desenhador de esquemas (ver abaixo). |
| **Browse LIF** | Volta a mostrar qualquer resultado anterior da pasta monitorizada. A primeira opção, **Em branco**, retira o resultado de todos os ecrãs. |

## Sobreposições

As sobreposições são o que se mostra **por cima** (ou em vez) dos resultados: texto, proteção de ecrã, vista de linha, relógio, recordes e contagem decrescente. Três pontos importantes sobre o seu funcionamento:

- **Pode ter várias em simultâneo.** Por exemplo, um fundo de proteção de ecrã com uma contagem decrescente e uma faixa de texto por cima. Ativar uma já não desativa as outras.
- **Os widgets decidem o que se mostra onde.** Cada ecrã só mostra as sobreposições que o seu esquema atribuído contém — pelo que ecrãs diferentes podem mostrar combinações diferentes a partir de uma só secretária.
- **Um novo resultado limpa todas** e devolve cada ecrã aos resultados — para que os resultados ao vivo tenham sempre prioridade.

### Proteção de ecrã (imagem ou esquema)

Escolha **Image** (um gráfico associado — quadros de patrocinadores, avisos) ou **Layout** (qualquer esquema guardado mostrado como tomada total da área de proteção de ecrã). Escolha a fonte e prima **Display**. Uma vez definida a fonte, o botão Screensaver ativa-a diretamente.

### Contagem decrescente

Conta de forma decrescente até uma **hora-alvo**, lida a partir do relógio de cada ecrã. Introduza a hora (p. ex. 15:40) e Iniciar. No Construtor de esquemas pode definir a legenda (predefinição «Next Event In:»), se os segundos são mostrados, e o texto/tipo de letra/cor. Oculta-se ao chegar a zero e cede lugar a novos resultados e outras sobreposições.

### Records

Os recordes passam a ser mostrados como [momentos](#moments). Marque o recorde de um atleta no campo User 3 do FinishLynx (ex. `PB` ou `W50 WR`) e cada ecrã que usa momentos mostra um cartão de recorde quando o resultado é guardado. Para um recorde que o FinishLynx não marcou, prima **Seleção manual** na janela principal: 1. escolha a corrida, 2. escolha a marca, 3. escolha ou escreva o tipo de recorde.

![Seleção manual de recordes:](assets/records.png)

### Vista de linha

Envia a imagem de photo-finish mais recente para ecrãs com um widget de vista de linha. O controlo Rotation (s) define a frequência com que alterna entre a foto e o resultado.

## Tamanho do texto e modos de rotação

O tamanho de texto predefinido dos resultados ajusta-se com os botões **+** e **−** (os widgets de esquema têm o seu próprio Tamanho de Texto no Construtor de esquemas).

O modo de rotação determina como se apresentam os resultados com mais de 8 concorrentes:

| Modo | Comportamento |
|---|---|
| **Scroll** | As 3 primeiras linhas ficam fixas; as linhas 4+ percorrem os restantes concorrentes. |
| **Page** | Pagina: 1–8, depois 9–16, etc. em rotação. |
| **Scroll All** | As 8 linhas percorrem os concorrentes sem posições fixas. |

A velocidade de rotação de atletas predefinida é de **5 segundos**.

## Navegar e restaurar

**Browse LIF** lista resultados anteriores da pasta monitorizada para poder voltar a mostrar qualquer um — útil para oportunidades de fotografia ou para reapresentar uma série anterior. Abrir um ficheiro antigo no FinishLynx *não* perturba a apresentação ao vivo; apenas uma alteração genuína a um resultado o promove.

**Em branco**, no topo da lista, retira o resultado de todos os ecrãs e volta a *A aguardar resultados*. O próximo resultado guardado aparece normalmente.

## Ligar ecrãs {#connecting-screens}

Abra `http://<endereço>:3000/display` em cada ecrã; recebe automaticamente um número. A página **Screen QR Codes** (a partir do painel Screens, ou `/screens-overview`) mostra um código legível para cada página de ecrã, para apontar rapidamente um telemóvel, tablet ou browser de TV para a página certa.

No painel **Screens** atribui um esquema guardado a cada ecrã de forma independente e remove ecrãs que já não estão ativos. A secretária tem também uma pré-visualização de quadro de resultados integrada que espelha um ecrã real quando lhe atribui um esquema.

Os ecrãs recarregam-se sozinhos quando a aplicação reinicia e mantêm o número e o esquema. Para ver um esquema nos ecrãs reais, use **Pré-visualizar → Nos ecrãs** no Layout Builder.

## O Layout Builder

Abra o Layout Builder para criar esquemas a partir de widgets. Cada esquema tem uma forma de tela e um tema.

- **Comece** por um modelo, ou arraste widgets da lista à esquerda para a tela.
- **Selecione um widget** para o editar no painel **Widget** à direita. O essencial vem primeiro; o resto está em **Mais definições**. O painel **Tela** reúne as definições do esquema: nome, tema, forma, **Mostrar nos ecrãs** e **Momentos**.
- **O texto de um widget** arrasta-se diretamente na tela com o widget selecionado. Os elementos alinham-se entre si e podem ficar à esquerda, ao centro ou à direita.
- **Anule** com ⌘/Ctrl+Z e prima **?** para ver todos os atalhos. Os painéis laterais recolhem-se para dar mais espaço à tela.
- **Mostrar nos ecrãs** — assinale os ecrãs onde o esquema deve aparecer.
- **Pré-visualizar** — **No navegador** mostra o esquema aqui com dados de exemplo ou em direto. **Nos ecrãs** mostra-o em todos os ecrãs ligados até parar; depois cada ecrã volta ao seu esquema.

![O Construtor de esquemas — paleta de widgets à esquerda, tela do esquema ao centro e painel de propriedades (com o navegador de widgets) à direita](assets/Layout-Builder.png)

## Momentos {#moments}

Os momentos são cartões curtos que aparecem nos ecrãs quando um resultado é guardado. Ative-os por esquema: **Tela → Momentos → Usar momentos neste esquema**.

- **Após uma corrida, mostrar** — o **Vencedor** (com a diferença) ou o **Pódio**. Nas corridas para, o pódio é ordenado pela pontuação RAZA.
- **Photo-finish em chegadas renhidas** — aparece primeiro quando os dois primeiros estão a menos de 0,05 s (ajustável), com a imagem de chegada se o FinishLynx guardou uma para essa corrida.
- **Recordes do resultado** — cada atleta marcado no campo User 3 do FinishLynx tem o seu cartão. O recorde do vencedor vai no próprio cartão do vencedor.
- **Só finais** — ativo por predefinição: os cartões só aparecem em provas com «Final» no nome. Os recordes aparecem em qualquer eliminatória.
- **Mostrar sobre** — todo o ecrã, ou um só widget.

Cada cartão aparece uma vez por corrida, assim que o resultado é guardado — nunca ao recarregar uma página nem ao voltar a mostrar um resultado antigo. Na janela principal, **Testar** reproduz um cartão de exemplo em todos os ecrãs que usam momentos, e **Pódio** mostra os três primeiros do resultado atual, para cerimónias.

### Transição entre resultados

Quando surge o resultado de outra prova, passa primeiro uma transição de 2 segundos com o logótipo PolyField e depois os resultados entram linha a linha. Está ativa em todos os esquemas. Escolha **A transição mostra** para usar um dos seus esquemas (um painel de patrocinadores, por exemplo), ou desmarque **Transição entre resultados**.

## Resultados no ecrã

- **Entrada linha a linha** — um resultado novo entra linha a linha, vencedor primeiro. Um resultado corrigido faz deslizar as linhas para o novo lugar. Desmarque **Animar as linhas quando os resultados chegam ou mudam** no widget para desligar.
- **Texto que cabe** — nomes e títulos longos encolhem em vez de serem cortados.
- **Corridas para** — quando o ficheiro da prova dá aos atletas uma classe WPA, a tabela acrescenta as colunas **Classe** e **RAZA**, mantendo a ordem de chegada.
- **Sem nomes** — algumas corridas só têm dorsais; as linhas e os cartões mostram então o dorsal.
- **Temas** — resultados, quadros de concursos e relógios seguem o tema do esquema.

## Referência de widgets

| Widget | Mostra |
|---|---|
| Results Table | O resultado atual, com colunas, rotação e tamanho de texto configuráveis. |
| Multi-Result | Uma grelha de vários resultados (2×2 / 3×2), mais recentes ou em rotação. |
| Start List | A lista de partida da prova atual. |
| Running Clock / Stopped Time | Relógio ao vivo ou congelado. |
| Event Name / Wind | Nome e vento da prova atual ou do resultado. |
| Custom Text / Logo / Time of Day | Texto estático, uma imagem/logótipo, ou a hora. |
| Field Results / Recent Results / Lançamentos / Jump Ruler / Vertical Jumps (PolyField) | Ecrãs de concursos em direto alimentados pelo PolyField Server, agrupados em **PolyField Server**. Ver [Lançamentos](#throws-display), [Saltos horizontais](#horizontal-jump-displays) e [Saltos verticais](#vertical-jump-displays). |
| Sobreposições Text / Screensaver / Line View / Clock | A faixa de texto, a imagem/esquema de proteção de ecrã, o photo-finish e o relógio em ecrã inteiro (mostrados quando o operador aciona a sobreposição correspondente). |
| Countdown Overlay | Contagem decrescente até uma hora-alvo com uma legenda editável. |

## Pontos de provas combinadas

Para uma competição de provas combinadas, a tabela de resultados pode mostrar uma coluna adicional **Combined Event** (prova combinada) que pontua cada marca de pista segundo as **tabelas oficiais 2026 UKA/ESAA de provas combinadas**.

![Um resultado 80mH U14B com a coluna de pontos de prova combinada — pontos por atleta e sem pontuação para DNF/DQ](assets/combined-events.png)

- **Adicionar a coluna** — no Construtor de esquemas, selecione um widget **Results Table** ou **Multi-Result** e adicione a coluna **Combined Event** (Propriedades → Colunas). Marque **Anexar «pts» à coluna de pontos de provas combinadas** para mostrar `617 pts` em vez de `617`.
- **Automático por prova e sexo** — a tabela é escolhida a partir do nome da prova (p. ex. `80mH (76.2) U14B`), cobrindo todas as categorias — de U13 a U20, Sénior e Masters — sem configuração por atleta.
- **Apenas pista** — as barreiras e as corridas planas são pontuadas; os concursos, as estafetas e qualquer prova sem tabela correspondente ficam em branco.
- **Não classificados** — os atletas DNS não são mostrados; DNF e DQ não mostram pontuação.

O tempo usado na pesquisa é o valor apresentado (já arredondado à precisão da cronometragem), pelo que os pontos correspondem exatamente às tabelas oficiais.

## Ecrãs de saltos horizontais {#horizontal-jump-displays}

Estes widgets mostram dados de concursos em direto do **PolyField Server** na mesma rede. Adicione-os a partir do grupo **PolyField Server** do Layout Builder. Defina o endereço do servidor uma só vez na janela principal, em **PolyField Server**; todos os widgets de concursos o usam.

### Jump Ruler (PolyField)

Uma régua junto à caixa de saltos para **salto em comprimento e triplo salto** — ideal para uma tira LED longa e estreita ao lado da pista de balanço (p. ex. 500 mm × 4–6 m). Desenha uma escala de distâncias com marcas ao metro / 50 cm / 10 cm, assinala os três melhores saltos e mostra os dados do saltador atual.

![O Jump Ruler no Construtor de esquemas — a escala ancorada à caixa com o saltador atual, o saltador anterior, os pinos do top 3 e a média da competição](assets/jump-ruler.png)

- **Segue a prova em curso.** Por predefinição, a régua mostra a prova de saltos horizontais em curso e passa sozinha à seguinte. Para réguas em zonas diferentes, assinale as provas de cada uma. As réguas novas colocam o texto numa faixa acima dos marcadores.
- **Tábua de chamada.** A escala está ancorada à caixa: introduza o **início da régua** para o salto em comprimento e para cada tábua do triplo salto (**7 / 9 / 11 / 13 m**, com 2 casas decimais, p. ex. `11.02`). A tábua ativa do atleta (fornecida pelo fluxo) determina o início usado, para que as marcas caiam sempre no sítio certo.
- **Pinos do top 3.** As três melhores marcas surgem como pinos de alturas decrescentes (1.º o mais alto, depois 2.º e 3.º), com o 1.º sempre à frente. Uma marca fora do intervalo visível surge como uma **seta** na extremidade a apontar na sua direção.
- **Pino de média.** Um pino **Avg** opcional traça a média da competição.
- **Painel do atleta.** Posicione cada elemento por arrasto — **atleta atual**, marca e vento atuais, **atleta anterior** com a sua marca e vento, tábua atual e melhor marca da competição — e defina para cada um a **legenda, a cor, o tamanho** e a visibilidade. Disponha-os como faixa superior ou painel lateral.
- **Sentido de corrida.** Escolha **esquerda → direita** ou **direita → esquerda** para que a escala corresponda ao sentido de balanço dos atletas para a caixa.
- **O fluxo:** um atleta é selecionado → mostrado como *atual* (ainda sem marca); o seu salto é medido → surgem a *marca e o vento atuais*; o atleta seguinte é selecionado → passa a *atual* e o anterior passa a *anterior*.

### Field Results & Recent Results (PolyField)

**Field Results (PolyField)** — um quadro de classificação ao vivo de concursos (posição, atleta, clube, prova, marca, melhor), com o líder em destaque e os nulos a vermelho.

![Field Results (PolyField) — classificação ao vivo de concursos com o líder em destaque](assets/field-results.png)

**Recent Results (PolyField)** — as três últimas marcas de concursos concluídas (nome, prova, ronda e marca, com vento nos saltos horizontais).

![Recent Results (PolyField) — as três últimas marcas de concursos concluídas](assets/recent-results.png)

## Ecrã de lançamentos {#throws-display}

**Lançamentos** mostra um concurso de peso, disco, martelo ou dardo a partir do PolyField Server, com cada queda marcada no setor e arcos de distância. Tal como os outros quadros de concursos, segue por predefinição a prova em curso.

- Os lançamentos do atleta atual, numerados por ronda; as quedas dos restantes como mapa de calor; a melhor marca do concurso como estrela dourada.
- O último lançamento aparece assim que é medido. Se passar para a liderança, passa primeiro uma faixa **NOVA MELHOR MARCA**.
- Atleta, clube, ronda, marca, posição, melhor marca e *marca para liderar* são textos que se posicionam livremente.
- **Painel LED pequeno** aumenta os marcadores e retira o detalhe fino para painéis LED de baixa resolução. O setor ocupa uma área que dimensiona, sem nunca tocar no texto.
- Requer a versão do PolyField Server que envia as coordenadas de queda rodadas.

## Ecrãs de saltos verticais {#vertical-jump-displays}

**Vertical Jumps** mostra um concurso de **salto em altura ou com vara**. Tal como os outros quadros de concursos, segue por predefinição a prova em curso; assinale provas para ligar um quadro à sua zona. Está no grupo **PolyField Server** e tem dois estilos.

### Avançado — quadro de qualificação

Uma barra horizontal, com a altura atual, divide o ecrã como um quadro de qualificação.

![Vertical Jumps (PolyField), estilo avançado — a barra com a altura atual, os atletas que transpuseram acima com um ponto verde e o atleta eliminado numa linha vermelha](assets/vertical-jumps.jpg)

- Os atletas que ainda têm de transpor ficam **abaixo** da barra. Quando um **transpõe**, passa para **cima** com um **ponto verde**; uma **falha** mostra um **ponto vermelho** e permanece abaixo; um atleta **eliminado** tem uma **linha vermelha**.
- Quando a **altura muda**, a barra surge com uma animação, todos os atletas voltam para baixo da barra e os eliminados desaparecem. Os atletas que **passam** a altura não são mostrados.
- A posição vertical da barra acompanha a proporção entre transpostos e não transpostos; se houver mais atletas do que linhas, a lista **roda** para mostrar todos.
- Os dados ficam alinhados em colunas (lugar · nome · tentativas · marcador) para se manterem organizados independentemente do comprimento dos nomes.

### Simplificado — cartão do estado atual

Um único cartão que mostra o atleta em ação: a altura atual, o seu nome, as suas tentativas nessa altura e a sua série completa.

![Vertical Jumps (PolyField), estilo simplificado — a altura atual, o atleta e as tentativas](assets/vertical-jumps-simple.jpg)

Cada elemento — nome da prova, altura, atleta, tentativas, série, e opcionalmente lugar / melhor / dorsal — é **posicionado por arrastamento** com a sua própria **legenda, cor, tamanho** e visibilidade, como o painel do Jump Ruler.

### Opções comuns

- **Sem altura definida.** Antes de uma altura ser anunciada (mostraria `0,00 m`), o widget mostra o **nome da prova e um logótipo de patrocinador** em vez disso.
- **Logótipo de patrocinador.** Opcional — mostrado nesse cartão de espera e (no estilo avançado) sob a barra durante a mudança de altura.
- **Configurável** — linhas, tamanho do texto e tipo de letra, cores (barra, transposto, falha, eliminado, destaque) e a duração da animação da barra.

## Temas, dorsais e abreviaturas de clubes

Os **temas** definem as cores predefinidas de todos os ecrãs; pode criá-los, duplicá-los e editá-los. Os **dorsais** podem ser mostrados ou ocultados na vista de resultados. As **abreviaturas de clubes** são geridas de forma centralizada (edite a lista de clubes) e aplicadas em todo o lado — adicione um novo clube ou substitua uma abreviatura integrada, e as alterações chegam a todos os ecrãs em poucos segundos.

## Vistas web

As vistas web acedem-se melhor através da interface web, usando os dados de acesso no topo da aplicação de secretária. Páginas principais:

| Página | URL |
|---|---|
| Quadro de resultados (esquema ativado) | `/scoreboard` |
| Ecrã de apresentação | `/display` |
| Vista Multi-Result | `/results` |
| Quiosque de atletas | `/athlete` |
| Quadro de velocidade | `/speed` |
| Relógio em curso | `/clock` |
| Classificações RAZA | `/raza` |
| Códigos QR dos ecrãs | `/screens-overview` |

### Vista Multi-Result

Apresenta resultados numa matriz 2×2 ou 3×2. Configure-a para mostrar os resultados mais recentes ou percorrer todos os resultados disponíveis; adapte o tamanho do texto; e use o modo de ecrã inteiro para ocultar a barra de ferramentas (qualquer movimento do rato fá-la reaparecer). Os resultados paginam, com a página atual mostrada no topo. O ícone de pesquisa abre o quiosque de atletas.

![Vista Multi-Result — uma grelha 2×2 de resultados com a barra de ferramentas na parte inferior](assets/multi-result.png)

### Quiosque de atletas (autoatendimento)

Abra `<ENDEREÇO-IP>:3000/athlete`. Um atleta pesquisa por nome ou número de dorsal; ao clicar num nome mostram-se todas as suas marcas na pasta de resultados atual. Ao clicar num cartão de resultado, este é apresentado em ecrã inteiro para oportunidades de fotografia. **Reset** limpa a pesquisa; o botão anterior regressa ao campo de pesquisa.

![O quiosque de autoatendimento de atletas — pesquisa por nome ou número de dorsal](assets/athlete-kiosk.png)

## Configuração do FinishLynx e TimeTronics {#finishlynx-setup}

- **Scripts de quadro de resultados** — use os scripts fornecidos `polyfield.lss`, `polyfield-wind.lss` e `polyfield-backup.lss` para que o FinishLynx envie o relógio em curso, o vento, as listas de partida e os resultados para o PolyField & Track Display. Consulte **[Configuração do quadro de resultados](#scoreboard-setup)** abaixo para configurar cada saída.
- **Recordes** — marque o recorde de um atleta no campo **User 3** do FinishLynx (p. ex. `PB` ou `W50 WR`). Os códigos de recorde são expandidos para títulos completos a partir da lista de clubes.
- **Vista de linha** — exporte as imagens de photo-finish (JPG) para a pasta de resultados monitorizada; o botão Line View ativa-se assim que estas surgirem.
- **Resultados** — guarde o seu LIF normalmente; o PolyField só apresenta resultados guardados.

### Configuração do quadro de resultados (FinishLynx) {#scoreboard-setup}

O PolyField & Track Display recebe o relógio em curso, as listas de partida, os resultados ao vivo e o vento através de um único fluxo UDP na **porta 5001**. O FinishLynx envia isto através das suas saídas **Scoreboard** (**Options → Scoreboard**). Configure as saídas abaixo — cada uma é um quadro **Network (UDP)** apontado ao computador que executa o PolyField & Track Display.

**Definições comuns a todas as saídas:**

| Definição | Valor |
|---|---|
| Serial Port | Network (UDP) |
| Port | `5001` |
| IP Address | o IP do computador que executa o PolyField & Track Display |
| Code Set | Single Byte |
| Results | Auto · Paging on |

#### 1. Saída principal — `polyfield.lss`

O fluxo primário: relógio em curso, listas de partida e resultados ao vivo.

![Definições de Scoreboard do FinishLynx para a saída principal do PolyField & Track Display](assets/scoreboard-main.png)

- **Script:** `polyfield.lss` · **Name:** PolyField & Track Display
- **Running Time:** Normal
- **Running Time → Options:** *Send results if armed* ✓
- **Auto Break:** *Finish* ✓ (com *if capturing* ✓)
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓ (deixe *Affiliation abbreviation* desligado — o PolyField & Track Display expande os nomes de clubes a partir da sua própria lista de clubes)

#### 2. Saída de vento — `polyfield-wind.lss`

Uma saída dedicada às leituras de vento.

![Definições de Scoreboard do FinishLynx para a saída de vento](assets/scoreboard-wind.png)

- **Script:** `polyfield-wind.lss` · **Name:** PolyField & Track Display Wind
- **Running Time:** **Raw** — o vento dispara a cada corte de feixe; o modo Raw passa cada leitura diretamente (o PolyField & Track Display ignora os valores «no data»)
- **Running Time → Options:** *Send results if armed* desligado
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Affiliation abbreviation* ✓ · *Track live results* ✓

#### 3. Saída de reserva — `polyfield-backup.lss` (recomendado)

Uma segunda cópia independente da **lista de partida** para maior resiliência. O FinishLynx envia cada lista de partida apenas uma vez quando a prova carrega, pelo que um único pacote UDP perdido pode deixar um ecrã em branco. Esta saída de reserva envia uma lista de partida idêntica a partir de um quadro separado, para que, se um pacote se perder, o outro ainda chegue. Aponte-a ao **mesmo** computador do PolyField & Track Display.

![Definições de Scoreboard do FinishLynx para a saída de reserva da lista de partida](assets/scoreboard-backup.png)

- **Script:** `polyfield-backup.lss` · **Name:** PolyField & Track Display Backup
- **Running Time:** Normal
- **Running Time → Options:** *Send results if armed* ✓
- **Results → Options:** *Always send place* ✓ · *Include first name* ✓ · *Track live results* ✓

> As três saídas podem funcionar em simultâneo e enviar para o mesmo IP e porta — o PolyField & Track Display distingue-as pelo conteúdo.

## Transmissão com OBS {#webcasting}

Use o PolyField & Track Display como camada gráfica transparente sobre uma transmissão de vídeo no OBS.

1. Crie um esquema para a transmissão — o modelo **Rótulo para transmissão** é um bom ponto de partida. Mantenha os widgets nas margens da imagem.
2. No OBS adicione uma fonte **Navegador**, 1920 × 1080, com o endereço `http://<endereço>:3000/display/<número>?transparent=1`.
3. No Layout Builder, assinale esse ecrã em **Mostrar nos ecrãs** no seu esquema de transmissão.

Tudo o que não é widget fica transparente, e os widgets ainda sem dados ficam ocultos. Desmarque **Transição entre resultados** no esquema de transmissão para que a transição não tape a câmara.

> **Transmitir sem gastar os dados da rede de resultados** — se a sua rede de resultados usa um cartão SIM 4G, ligue o computador do OBS às duas redes e não atribua gateway predefinido ao adaptador da rede de resultados. A transmissão sai então pela outra ligação.

## Rede

- A aplicação serve na **porta 3000** e anuncia-se como `display.local`, para que os ecrãs usem `http://display.local:3000` sem saber o IP. Os ecrãs configurados com o antigo `track.local` continuam a funcionar.
- Defina o endereço do **PolyField Server** uma só vez na janela principal; todos os widgets de concursos o usam.
- Em computadores com mais do que uma placa de rede (comum no Windows), escolha a placa de rede correta no painel de ligação para que o endereço certo seja anunciado.
- Todos os dispositivos têm de estar na mesma rede que o computador anfitrião.

## Resolução de problemas

| Sintoma | Verifique |
|---|---|
| O botão Line View está desativado | Ainda não há JPGs de photo-finish na pasta monitorizada — verifique o caminho de exportação de imagens do FinishLynx. |
| Nenhum cartão de momento aparece | O esquema tem de ter os momentos ativos. Com **Só finais**, o nome da prova tem de conter «Final». Cada corrida aparece uma vez por ecrã, por isso guardar de novo o mesmo ficheiro não a repete. |
| Um ecrã mostra «à espera de esquema» | Atribua um esquema a esse ecrã no painel Screens. |
| Reapareceu um resultado antigo | Abrir um ficheiro no FinishLynx já não o promove; só uma alteração real o faz. Use Browse LIF para reapresentar resultados anteriores de forma intencional. |
| Os ecrãs não se ligam | Confirme a mesma rede, a porta 3000 acessível e (em PCs com várias placas) a placa de rede correta selecionada. |

## Descarregar e suporte

Descarregue a versão mais recente em [www.polyfield.co.uk](https://www.polyfield.co.uk) ou na [página de versões](https://github.com/KingstonPolyAC/PolyField-and-Track-Display/releases). Suporte: [support@polyfield.co.uk](mailto:support@polyfield.co.uk).

## Integração via API {#api-integration}

O PolyField & Track Display serve uma pequena **API HTTP + JSON só de leitura** na **porta 3000**, na **mesma rede local** dos seus ecrãs. É a mesma interface que os ecrãs integrados usam, pelo que qualquer coisa na LAN — um quadro de resultados personalizado, um painel de estatísticas, uma sobreposição de streaming, a sinalização própria de um recinto — pode ler os resultados ao vivo, a lista de partida e o relógio em curso diretamente da aplicação. Os pedidos são `GET` simples, as respostas são JSON, não há autenticação e o CORS está aberto, pelo que uma página de browser na LAN pode chamá-la diretamente.

A API é **apenas para LAN por conceção** — a aplicação não a expõe à internet. **Qualquer integração voltada para a WAN ou a internet** (quadros de resultados remotos, serviços na nuvem, um segundo recinto) **deve ser discutida connosco primeiro** para ser feita em segurança, normalmente através de uma VPN ou de um proxy inverso controlado, em vez de abrir a porta ao mundo. Contacte [support@polyfield.co.uk](mailto:support@polyfield.co.uk).

**URL base:** `http://<ip-do-pc-track>:3000` — encontre o endereço LAN do PC no painel **Displays**, ou em `GET /server-info`.

| Método e caminho | Devolve |
|---|---|
| `GET /server-info` | O IP LAN do PC. |
| `GET /latest-lif` | O resultado atual (o que está nos ecrãs). `{}` quando não há. |
| `GET /all-lif` | Um array de todos os resultados recentes, do mais recente para o mais antigo. |
| `GET /startlist` | A lista de partida da prova atual. |
| `GET /clock-data` | O relógio em curso ao vivo (atualiza continuamente). |

### `GET /server-info`

```json
{ "lanIP": "192.168.0.137" }
```

### `GET /latest-lif` e `GET /all-lif`

`/latest-lif` devolve um objeto de **resultado** (`{}` quando nada está carregado); `/all-lif` devolve um **array** do mesmo objeto, do mais recente para o mais antigo. Campos:

- `fileName` — nome do ficheiro de origem.
- `eventName` — título da prova tal como enviado pelo sistema de cronometragem.
- `wind` — leitura de vento com unidade (p. ex. `"0.6 m/s"`), ou vazio.
- `modifiedTime` — segundos Unix da última alteração do resultado.
- `competitors[]` — uma entrada por atleta: `place`, `id` (dorsal), `firstName`, `lastName`, `affiliation` (clube/país), `time` (já arredondado/formatado), e opcionalmente `recordFlag` (p. ex. `"PB"`, `"W50 WR"`).

```json
{
  "fileName": "race01.lif",
  "eventName": "Men 100m Final",
  "wind": "0.6 m/s",
  "modifiedTime": 1790447000,
  "competitors": [
    { "place": "1", "id": "1001", "firstName": "Marcell", "lastName": "JACOBS",   "affiliation": "ITA", "time": "9.80", "recordFlag": "PB" },
    { "place": "2", "id": "1002", "firstName": "Fred",    "lastName": "KERLEY",   "affiliation": "USA", "time": "9.84" },
    { "place": "3", "id": "1003", "firstName": "Andre",   "lastName": "DE GRASSE", "affiliation": "CAN", "time": "9.89" }
  ]
}
```

### `GET /startlist`

- `eventName`, `round`, `heat`, `eventNo` — identidade da prova (qualquer um pode estar vazio).
- `hasLanes` — `true` para provas por corredor (pista), `false` caso contrário.
- `entries[]` — `lane` (corredor), `id` (dorsal), `firstName`, `lastName`, `affiliation`.

```json
{
  "eventName": "T1 Kestrel Club 75 Race 1 of 6",
  "round": "",
  "heat": "",
  "eventNo": "",
  "hasLanes": true,
  "entries": [
    { "lane": "1", "id": "164", "firstName": "Rocco",  "lastName": "Kothakota", "affiliation": "St Mary's Richmond AC" },
    { "lane": "2", "id": "60",  "firstName": "Fabian", "lastName": "Higgins",   "affiliation": "Young Athletes Club (YAC)" }
  ]
}
```

### `GET /clock-data`

O relógio ao vivo do sistema de cronometragem. Sonde-o (cerca de uma vez por segundo) para acionar um relógio em curso. `state` é `armed` / `running` / `stopped` / `idle`; `serverNow` é a hora do servidor em milissegundos Unix, para que um cliente possa corrigir o desvio do relógio.

```json
{
  "state": "running",
  "time": "9.42",
  "eventName": "Men 100m Final",
  "eventNo": "12",
  "round": "1",
  "heat": "3",
  "wind": "+0.6",
  "receivedAt": 1790447079000,
  "serverNow": 1790447079466
}
```

Os resultados e a lista de partida mudam com pouca frequência — sonde a cada 1–2 segundos (ou obtenha a pedido); só o `/clock-data` precisa de sondagem frequente enquanto uma corrida está a decorrer.
