# A+ Gestão

Aplicação web estática (HTML + CSS + JavaScript) para o GitHub Pages. Sem servidor e sem custo.

## Publicar
1. Crie o repositório `a-mais-gestao` (Public) e envie estes arquivos para a raiz.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Para atualizar, substitua o `index.html` no repositório. Seus dados não são afetados.

## Como o sistema está organizado
- **Hoje**: o que precisa de ação (tarefas, entregas, visitas, contas a vencer, produtos para repor) e os números do mês.
- **Lojas**: cada parceiro com estoque na loja, vendido e a receber. O botão Acertar fecha as consignações pendentes.
- **Pedidos**: quadro por etapa (orçamento até entregue), com botão Avançar.
- **Estoque**: calculado sozinho (inicial + lotes + entradas − vendas diretas − envios para lojas).
- **Finanças**: lançamentos e caixa.
- **Mais**: os demais cadastros (produção, custos, contatos, metas…) e o backup.
- **+ Registrar** (canto superior direito) cria venda, envio, pedido, despesa etc. de qualquer tela.

## Digitação automática
- **Ctrl+K**: abre a busca rápida. Enter abre o módulo; Shift+Enter já abre um registro novo.
- **Ctrl+Enter** no formulário salva e abre outro em branco. **Duplicar** copia um registro.
- Códigos novos (LOJ-001, OP-001, PED-001…) e datas (hoje) vêm preenchidos.
- **SKU ou nome do produto** preenche produto, custo (usa Custos reais, senão o cadastro) e preço (pelo canal, usando a Matriz de preços).
- **Loja** preenche a comissão. **Contato/empresa** preenche pessoa, telefone e cidade. **Material** preenche unidade e custo.
- Totais, lucro, comissão, saldo, margem, % de perda, atraso e situação são calculados na hora (campos verdes). Se você digitar num campo calculado, ele deixa de ser recalculado.
- Categoria, canal, forma de pagamento, cidade, responsável, fornecedor, unidade, cor e similares viram **listas de escolha** que aprendem com o que você já cadastrou. Só valores inéditos exigem digitar (opção ➕ Novo…), e o último valor usado já vem preenchido.

## Dados
Ficam no `localStorage` do navegador (mesma chave da versão anterior, então os registros antigos continuam). Use **Backup Excel** ou **Backup JSON (completo, sem perdas)** no painel com frequência. O painel avisa quando o último backup passa de 7 dias.
Próxima etapa: sincronizar com o Supabase (nunca coloque a chave `service_role` no site).

## Regras dos números (v2)
- **Vendido no mês** = vendas diretas (exceto canal CONSIGNADA e EVENTO) + consignações **acertadas** no mês + pedidos **entregues** no mês + eventos do mês. Não lance a mesma venda em dois lugares.
- **Acertar** lança uma entrada RECEBIDA no caixa e pergunta quantas unidades sobraram e voltaram para casa; o resto vira nova linha em aberto na loja.
- **Saldo do caixa** ignora lançamentos PENDENTE/ATRASADO/CANCELADO.
- Renomear loja ou SKU atualiza os registros ligados a eles.
- **Seleção em massa:** nas listas, marque as caixinhas (ou a do cabeçalho; Shift seleciona um intervalo) para **Editar em massa** (troca um campo em todos os selecionados) ou **Excluir selecionados**. A seleção vale só para o que está visível com a busca/filtro atual.

## Jarvis (assistente com Gemini)
Botão **J** no canto inferior direito (ou Ctrl+J). Na engrenagem ⚙, cole sua chave gratuita do Google AI Studio (fica só no seu navegador, fora dos backups), escolha a voz (Charon, Puck, Kore, Fenrir ou Aoede, as mesmas do Gemini Live). O Jarvis recebe um **resumo agregado** dos seus números (sem telefones) a cada pergunta. Microfone 🎤 funciona no Chrome/Edge.
