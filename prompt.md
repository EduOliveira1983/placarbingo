Quero que você gere um arquivo chamado `index.html` que implemente um marcador de bingo totalmente funcional com as seguintes características:

1. Estrutura básica:
- Documento HTML5 começando com `<!DOCTYPE html>`.
- Atributo `lang="pt-br"` no `<html>`.
- `<head>` com `<meta charset="utf-8">`, `<meta name="viewport" content="width=device-width, initial-scale=1">`, título "Marcador de Bingo" e importação do Tailwind CSS via CDN.
- Dentro de `<style>`, inclua:
  - Suavização de fontes (`-webkit-font-smoothing`, `-moz-osx-font-smoothing`).
  - Classe `.firework` (quadrado vermelho 8x8px arredondado, animado com `@keyframes explode` que sobe e desaparece).
  - Classe `.fade` com transição de opacidade.

2. Layout do `<body>`:
- Classe geral: `bg-neutral-50 text-neutral-900 min-h-dvh flex flex-col`.
- Container principal (`div`) com `w-full px-4 py-6 flex flex-col gap-6 flex-grow`.

3. Cabeçalho fixo no topo:
- Input numérico (`id="numberInput"`) com placeholder "Digite o número e pressione Enter", estilizado com Tailwind, e mensagem de erro (`id="message"`) logo abaixo, usando `.fade`.
- No centro, exibir o tipo de jogo (`id="gameTypeDisplay"`) em **texto grande (7xl)**, padrão "CARTELA CHEIA".
- À direita, botões:
  - Configurações (`id="btnConfig"`, texto "C").
  - Desfazer (`id="btnUndo"`, texto "D", desabilitado inicialmente).
  - Refazer (`id="btnRedo"`, texto "R", desabilitado inicialmente).
  - Limpar (`id="btnClear"`, texto "L") → ao clicar deve exibir **confirmação via `confirm()` antes de limpar histórico**.
  - Bingo (`id="btnBingo"`, verde, texto "BINGO!").
- Linha de ajuda embaixo com atalhos (C = Configurações, etc.).

4. Quadro central (`section id="board"`) onde aparecem as colunas B-I-N-G-O e os números chamados:
- Cada coluna mostra:
  - Letra no topo (5xl bold).
  - Intervalo abaixo (ex: 1–15).
  - Lista de números chamados.
- **Números:**
  - Sempre exibidos com zero à esquerda (ex: 01, 09, 15).
  - Classe `text-4xl font-extrabold`.
  - Dispostos em **grid de 4 colunas**, sem bordas extras, só espaçamento entre eles.
  - Último número chamado destacado com `underline` e `decoration-indigo-500`.

5. Rodapé fixo:
- À esquerda: título "PRÊMIO" e valor (`id="prizeDisplay"`, inicial "—").
- À direita: título "ÚLTIMA PEDRA" e valor (`id="lastCalled"`, inicial "—", exibido em fonte muito grande 7xl bold).

6. Modal de configurações (`id="settingsModal"`):
- Caixa central com título "Configurações", botão "Fechar".
- Botões de presets: BINGO, AJUDE, AJUDA.
  - Importante: **mesmo se a palavra tiver mais ou menos letras que "BINGO", deve-se usar apenas 5 colunas e cada faixa mantém 15 números (1–15, 16–30, 31–45, 46–60, 61–75)**.
- Formulário (`id="settingsForm"`) com:
  - Grid editável de letras e intervalos (`id="letterGrid"`).
  - Checkbox (`id="orderCheckbox"`) para mostrar em ordem de chamada ou numérica.
  - Select (`id="gameTypeSelect"`) com opções "CARTELA CHEIA" e "QUINA".  
    - O valor selecionado também deve aparecer no cabeçalho em texto **bem grande**.
  - Input de texto (`id="prizeInput"`) para prêmio.
  - Botões: "Adicionar letra" (`id="btnAddLetter"`) e "Salvar".

7. Overlay de vitória (`id="bingoOverlay"`) cobrindo a tela inteira com fundo preto translúcido e texto amarelo gigante "BINGO!" animado em bounce.

8. Script `<script>`:
- Todos os botões de controle recebem classes extras (`size-10`, `grid`, `place-items-center`, etc.).
- Uso de `localStorage` para salvar e carregar:
  - Configuração (`bingo.config`), histórico (`bingo.history`), pilha de refazer (`bingo.redo`), ordem (`bingo.order`), prêmio (`bingo.prize`), tipo (`bingo.type`).
- Configuração padrão: letras B-I-N-G-O, com intervalos 1–15, 16–30, 31–45, 46–60, 61–75.
- Funções:
  - `save` e `load` para persistência.
  - `inRange` para validar número dentro do intervalo.
  - `last` retorna último número chamado.
  - `badge` cria `<span>` para cada número (2 dígitos, fonte grande).
  - `showMessage` mostra erro temporário.
  - `refreshColumns` atualiza quadro com histórico.
  - `renderBoard` monta grid das colunas.
  - `commitNumber` adiciona número se válido.
- Eventos:
  - Input Enter → chama `commitNumber`.
  - Undo/Redo/Limpar funcionam e atualizam histórico.
    - Limpar deve pedir confirmação antes de zerar.
  - Botão Config abre modal; Fechar fecha.
  - Botões presets alteram letras, mas sempre com 5 colunas e intervalos de 15 números.
  - Submit do formulário salva configurações e atualiza tela.
  - Botão BINGO mostra overlay, gera fogos (30 divs `.firework` com `setTimeout` para remover), depois esconde overlay em 3s.
- Inicialização chama `renderBoard()`.

O resultado deve ser um arquivo HTML completo, auto-contido e funcional, idêntico ao descrito.
