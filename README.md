# A+ Gestão

Aplicação web estática (HTML + CSS + JavaScript) para o GitHub Pages. Sem servidor e sem custo.

## Publicar
1. Crie o repositório `a-mais-gestao` (Public) e envie estes arquivos para a raiz.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Para atualizar, substitua o `index.html` no repositório. Seus dados não são afetados.

## Digitação automática
- **Ctrl+K**: abre a busca rápida. Enter abre o módulo; Shift+Enter já abre um registro novo.
- **Ctrl+Enter** no formulário salva e abre outro em branco. **Duplicar** copia um registro.
- Códigos novos (LOJ-001, OP-001, PED-001…) e datas (hoje) vêm preenchidos.
- **SKU ou nome do produto** preenche produto, custo (usa Custos reais, senão o cadastro) e preço (pelo canal, usando a Matriz de preços).
- **Loja** preenche a comissão. **Contato/empresa** preenche pessoa, telefone e cidade. **Material** preenche unidade e custo.
- Totais, lucro, comissão, saldo, margem, % de perda, atraso e situação são calculados na hora (campos verdes). Se você digitar num campo calculado, ele deixa de ser recalculado.
- Campos como canal, forma de pagamento, cidade e responsável sugerem o que você já digitou antes e lembram o último valor usado.

## Dados
Ficam no `localStorage` do navegador (mesma chave da versão anterior, então os registros antigos continuam). Use **Backup Excel** no painel com frequência. O painel avisa quando o último backup passa de 7 dias.
Próxima etapa: sincronizar com o Supabase (nunca coloque a chave `service_role` no site).
