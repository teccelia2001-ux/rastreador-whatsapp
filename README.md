# Rastreador de número — WhatsApp

Informa todas as mensagens de um grupo que citam um determinado número,
organizadas por data. Usa o mesmo coletor por favorito do termômetro
(`busca-servico-obras`), só que espelhando a tela do WhatsApp Web.

- **Link público:** https://teccelia2001-ux.github.io/rastreador-whatsapp/
- **Fontes na máquina:** `PROJETOS CLOUDE/rastreador-whatsapp/`

## Como funciona

O WhatsApp exige login, então a coleta roda dentro dele por um favorito do
navegador (bookmarklet). O coletor **espelha a tela**: lê as mensagens da
conversa aberta pelo `data-pre-plain-text` — o atributo em que o próprio
WhatsApp guarda data, hora e autor de cada balão —, sobe o histórico e só para
quando a contagem deixa de crescer, mesma lógica do coletor do termômetro. Dá
para limitar quantas mensagens subir, e o painel do canto tem botão de parar
aproveitando o que já veio.

Nada é escrito no grupo, nada é enviado para lugar nenhum e nenhum arquivo é
baixado: o resultado vai para a área de transferência e você cola de volta aqui.

A busca ignora ponto, traço, barra e espaço — `0032503170` também encontra
`003.250.3170` e `0032-503170`. Marcando *só o número inteiro*, ele para de
casar dentro de números maiores.

Caminho alternativo: a **Exportar conversa (sem mídia)** do próprio WhatsApp
gera um `.txt` que também pode ser arrastado para a página. Serve para
histórico antigo e para conferir a coleta. As duas fontes podem conviver.

## Arquivos

Um arquivo só — `index.html`, com tela, estilo e código dentro. Sem build e sem
dependência externa. Publicar é `git commit` + `git push`; o GitHub Pages
republica sozinho em cerca de um minuto.

A última coleta aplicada fica no `localStorage` do próprio aparelho, com
proteção para o caso de ele estar bloqueado — aba anônima ou `file://` — em vez
de quebrar a página.
