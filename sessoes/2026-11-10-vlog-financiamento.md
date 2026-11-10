# Resumo da sessão — 10/11/2026 — Edição do "Vlog financiamento"

## Pedido
Editar o vídeo "vlog" (`Videos sem edição\vlog.mp4`) inspirado nas edições da pasta
`Referencia\motiron vlogs` e seguindo as cores da logo (azul, cinza, branco).

## O vídeo
Fala para a câmera, dentro do carro, 2min27, 478x850. Tema: quanto precisa de
entrada para financiar um imóvel (banco financia até 80%, entrada mínima 20%,
documentação 5 a 6%, o banco analisa entrada, renda e data de nascimento,
limite de 80 anos, fazer simulação antes de agendar a visita).

## Estilo das referências (motiron vlogs)
Vídeo de quem fala encolhe para um cartão arredondado sobre fundo claro;
tipografia animada misturando serifada itálica com palavra grande em negrito;
gráficos e cartões animados acompanhando a fala.

## O que foi entregue
Pasta: `Exportação\Vlog financiamento`
- `Vlog financiamento - editado.mp4` (1080x1920, 2min31, 124 MB)
- `Vlog financiamento - editado (leve).mp4` (720p, 23,7 MB, para celular)

## A edição tem
- Vídeo alternando entre tela cheia e cartão sobre fundo claro (21 cenas)
- Palavras-chave grandes em azul: "entrada", "20%", "5 a 6%", "renda", "simulação"
- Barra 80% banco / 20% entrada; tabelas dos exemplos (500, 250 e 300 mil)
  com números contando; checklist de documentação (Registro, ITBI, Engenharia);
  lista do que o banco analisa; régua do prazo até os 80 anos
- Balão de mensagem digitando "Qual o valor de entrada para o financiamento?"
- Legenda embaixo, palavra a palavra, com destaque azul
- Logo como marca d'água e barra de progresso no topo
- Final: logo + bordão digitado "AMJ, porque onde você vai viver, importa!"
  + botão "Faça sua simulação" piscando + "chame no direct"
- Áudio: redução de ruído "C", volume normalizado, whoosh (0,40) nas trocas
  de layout e ding (0,22) nos números principais

## Decisões tomadas sem consulta
(Resposta do usuário à entrega: "Boa")
- Velocidade original (1.0x), cortando só duas pausas longas
- Fontes: Inter + Instrument Serif itálica nas frases de apoio
- Sem música de fundo
- Linha "Para separar ≈ R$ 78 mil" no exemplo dos 300 mil (60 + 18),
  que não é dita literalmente na fala

## Como refazer / ajustar
- Script: `editor\scripts\build_vlog.py` (cortes, cenas, textos e correções de legenda)
  → gera `editor\public\cut-vlog.mp4` e `editor\public\edit-vlog.json`
- Visual: `editor\src\vlog\Vlog.tsx` e `Panels.tsx` (composição "Vlog" do Remotion)
- Render: dentro de `editor\`:
  ```
  npx remotion render Vlog "../Exportação/Vlog financiamento/<nome>.mp4" --crf=18
  ```
  (cerca de 30 min neste PC)

## Problemas encontrados e resolvidos
- A transcrição automática pulou uma frase inteira (exemplo dos 500 mil);
  foi recuperada retranscrevendo o trecho
- A redução de ruído travava o FFmpeg neste arquivo; resolvido fixando o
  formato de áudio antes do filtro
- O vídeo aparecia com barras pretas dentro do cartão; enquadramento refeito
- Cartão de valores ficava vazio por alguns segundos; corrigido e renderizado de novo

## Não foi feito
- Nenhuma skill nova foi baixada ou usada (só o editor Remotion + FFmpeg já instalados)
- Sem capa do Reel e sem música
