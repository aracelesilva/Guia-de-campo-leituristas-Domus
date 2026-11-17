# Plano do app e referências

## Rumo do projeto (definido em 16/11/2026)
O guia vai virar um **aplicativo dividido em duas áreas**:

1. **Área do Leiturista**: curso + consulta em campo, **por tipo de serviço**
   (Leitura Individual/Mensal, Leitura Inicial, Início de Medição, Vistoria,
   Central de Gás, Suspensão/Corte, Religue, Releitura).
2. **Área dos ADMs**: gestão (acompanhar quem fez o curso, conteúdo e
   novidades do OFS para repassar à equipe). Escopo detalhado a definir.

## Vídeo de referência: "Melhorias OFS Ultragaz" (v4)
Vídeo de 70 s, horizontal (1920×1080), sem áudio, feito pela Domus para
mostrar melhorias testadas no app OFS. **É o padrão visual para os vídeos
de tela do app.** O arquivo não fica neste repositório (o repositório é
público e o vídeo mostra nomes e endereços reais); a Aracele tem o original.

### Como ele é montado
- **Abertura:** título grande ("Melhorias OFS Ultragaz") com um traço laranja embaixo.
- **Fundo:** azul-claro com formas arredondadas em azul mais claro; logo Domus no canto inferior direito.
- **Layout de cada tela:** texto à esquerda e celular com a gravação de tela à direita.
- **Bloco de texto, sempre na mesma ordem:**
  1. Número do item num círculo laranja (1, 2, 3...)
  2. Título em preto e negrito
  3. "Resultado esperado" em laranja + uma frase explicando
  4. Selo verde "✓ STATUS: OK"
  5. Cartão branco com borda laranja: "PASSO 1 DE 3" + a instrução do passo
- **No celular:** cursor/toque marcado com um círculo, mostrando onde tocar.
- **Fechamento:** "Resumo dos testes", uma lista com cada item numerado e um selo verde "OK" que vai aparecendo um a um, e a assinatura "Domus Soluções".

### O que aproveitar no app
- Usar o mesmo formato "PASSO X DE Y" + gravação de tela nos vídeos de
  **como dar a baixa no OFS** de cada serviço.
- Cores batem com o app (laranja #F27820, azul-marinho, azul-claro).
- Os itens do vídeo viram conteúdo da trilha/lição do OFS:
  1. Prévia das OSs dentro da atividade agrupada, sem iniciar o pacote
  2. Busca da OS pelo número do medidor (filtro)
  3. Botão de flash nas atividades com foto (botão amarelo na câmera)
  4. Aviso de OS pendente antes de finalizar o pacote
  5. Sem "ocorrência em massa" em pacote com uma única OS
  6. Ocorrência em massa exige observação (sem ela o "Aplicar" fica bloqueado)

## Acessos (definido em 16/11/2026)
- **Leiturista:** entra com o mesmo cadastro do **Domus Frota** (base → nome → placa do carro).
  O guia consulta o Apps Script do Frota (`listarLeituristas` e `entrarLeiturista`).
  **Leiturista novo:** o gestor cria o perfil no Domus Frota; ele aparece no guia sozinho.
- **ADM principal (Aracele, aracele.silva@gmail.com):** vê e acessa tudo, cadastra os gestores.
- **Gestor:** entra com e-mail e senha e vê só as bases/regionais que a Aracele liberou para ele
  (aba "Gestores" da Área do ADM).

## Banco de dados
Supabase, projeto **Domus Gestão de Prazos**, tabelas separadas com prefixo `guia_`:
- `guia_eventos`: progresso enviado pelos celulares (lições lidas, respostas e resultado dos testes).
  Os celulares só conseguem **enviar**. Quem lê é o ADM: o master vê tudo; o gestor só as bases dele.
- `guia_avisos`: novidades publicadas pelos ADMs; todos os leituristas leem.
- `guia_admins`: quem é ADM (`papel` = master ou gestor) e quais `bases` cada gestor acompanha.

Observação: o login de ADM usa o mesmo sistema de contas do Domus Gestão. Quem cria a senha
pelo guia também ganha uma área pessoal vazia no Domus Gestão (comportamento do cadastro de lá).
