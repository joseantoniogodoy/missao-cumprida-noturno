# Missão Cumprida — Noturno

Jogo digital para a IV Mentoria de Professores Articuladores do Ensino Noturno. Quatro rodadas, nove cartas, imprevistos, registro de decisões, painel do formador, revelação após quatro rodadas e exportação CSV.

## Publicação no mesmo GitHub Pages

1. No repositório do jogo dos Coordenadores, crie a pasta `noturno`.
2. Coloque nela `index.html`, `app.js` e um `firebase-config.js` com a **mesma configuração Firebase** já utilizada pelo jogo anterior. O arquivo `firebase-config.example.js` serve de modelo.
3. Faça commit. Com GitHub Pages ativado, acesse `https://SEU-USUARIO.github.io/SEU-REPOSITORIO/noturno/?sala=articuladores-iv`.
4. No notebook do formador, abra `https://SEU-USUARIO.github.io/SEU-REPOSITORIO/noturno/?sala=articuladores-iv&painel=1`.
5. Cada equipe abre o link normal e informa um nome diferente.

A coleção Firestore utilizada é `missao_noturno_salas/{sala}/equipes/{id}`, diferente da coleção do jogo dos Coordenadores.

## Configuração e segurança

O jogo usa autenticação anônima do Firebase. Ative-a em Authentication. As regras Firestore devem permitir leitura/escrita da coleção para usuários autenticados, mas **não publique uma regra ampla sem antes limitar quem pode editar**. A versão inicial utiliza `painel=1` como controle de interface, **não como autenticação de administrador**; por isso é um protótipo para teste, e não um painel seguro para uso público. Antes da formação, configure permissões de administrador no Firebase (por exemplo, custom claims e regras restritas) e revise as operações de gravação.

O jogo usa dados fictícios. Não insira nomes, telefones ou informações identificáveis de estudantes.

## Teste local

Sirva a pasta com um servidor HTTP local (por exemplo, `python3 -m http.server 8000`) e abra `http://localhost:8000`. Sem `firebase-config.js` válido, funciona como demonstração local em um único navegador, sem sincronização entre notebooks.

## Atenção

Não substitua o `index.html` original do jogo dos Coordenadores: mantenha estes arquivos apenas na pasta `noturno`. A liberação dos resultados ocorre por equipe após a quarta rodada.
