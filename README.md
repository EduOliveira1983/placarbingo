Marcador de Bingo

Este repositório contém um experimento de criação de um placar de Bingo usando apenas o ChatGPT como ferramenta de desenvolvimento.

A ideia principal foi explorar até onde é possível chegar com um projeto relativamente simples utilizando apenas prompts, sem escrever o código manualmente.

📖 Contexto

O processo começou com a ideia de criar um marcador de bingo em HTML, CSS e JavaScript.
Foram feitos alguns rascunhos e, para ajudar na comunicação com o ChatGPT, foi produzido também um layout simples no Paint (layout.jpeg).

A partir disso, foram criados prompts e, após várias iterações, chegou-se ao arquivo final index.html.
Durante os testes, observou-se que nem sempre o ChatGPT gera o código exatamente igual ao esperado — o que faz parte do experimento.

Portanto, a proposta não é simplesmente usar o prompt para "gerar o projeto pronto", mas mostrar que:

É possível produzir algo funcional apenas com ChatGPT.

O processo envolve refinamento, ajustes e alternativas, como usar um layout de referência.

O prompt final serve como documentação do caminho percorrido.

📂 Estrutura do Repositório

index.html → código final do marcador de Bingo.

layout.jpeg → layout feito no Paint para guiar o ChatGPT.

prompt.md → prompt gerado a partir do código final, documentando como recriar o projeto.

README.md → este arquivo, explicando o projeto.

🧩 Funcionalidades do Marcador

Inserir números chamados, com validação (não repetir, respeitar faixas).

Histórico de números exibido em colunas com zero à esquerda.

Destaque para o último número sorteado.

Suporte a desfazer, refazer e limpar (com confirmação).

Modal de configurações para ajustar letras, intervalos, tipo de jogo e prêmio.

Tipos de jogo: Cartela Cheia e Quina.

Efeito de fogos e overlay animado ao declarar BINGO!.

Persistência no navegador usando LocalStorage.

🛠️ Como usar

Clone este repositório

Abra o arquivo index.html no navegador.

Comece a usar o marcador de bingo!

📌 Observações

O projeto é um experimento prático de uso do ChatGPT como ferramenta de prototipagem.

Pequenas diferenças podem ocorrer se tentar regenerar o código apenas pelo prompt — esse é justamente o aprendizado do processo.

A ideia pode ser expandida facilmente com novas regras ou personalizações.

🎯 Conclusão

Este repositório mostra como ChatGPT pode ser usado não apenas para responder perguntas, mas como uma ferramenta de criação de software.
Mesmo com algo simples como um marcador de Bingo, o processo exigiu refinamento de prompts, prototipagem visual (Paint) e iterações até alcançar o resultado final.
