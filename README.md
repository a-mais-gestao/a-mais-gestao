# A+ Gestão — versão inicial para GitHub Pages

Aplicação web estática em HTML, CSS e JavaScript, preparada para publicação gratuita no GitHub Pages. Não usa Replit nem exige créditos de IA.

## Como publicar gratuitamente
1. Crie um repositório no GitHub chamado `a-mais-gestao` e deixe-o **Public** se quiser usar o GitHub Pages gratuito.
2. Envie os arquivos desta pasta para a raiz do repositório. O arquivo principal deve ficar como `index.html` na raiz.
3. No GitHub, abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**, escolha `main` e `/ (root)`, e salve.
5. Aguarde a publicação indicada na própria tela do GitHub Pages.

## O que esta versão já faz
- Painel com indicadores calculados a partir dos registros locais.
- Módulos de produtos, vendas, consignações, lojas, pedidos personalizados, estoque, produção, custos, finanças, prospecção, oportunidades, metas, cidades, demanda e outros.
- Cadastro, edição, exclusão e busca em cada módulo.
- Exportação de backup Excel por módulo ou completo.
- Importação de backup Excel com prévia dos módulos e quantidade de registros antes de confirmar.
- Não contém registros fictícios pré-carregados.

## Limitação importante desta primeira versão
Os registros ficam no armazenamento local do navegador (`localStorage`), neste dispositivo. Isso é útil para validar a interface e o fluxo de trabalho, mas não sincroniza entre dispositivos e pode ser perdido se os dados do site forem apagados. Faça backups Excel regulares.

## Próxima etapa: Supabase
O projeto Supabase anterior pode ser reaproveitado. Antes de ativar sincronização, é necessário conferir a estrutura real das tabelas, finalizar a conta administrativa e configurar políticas de acesso. Nunca coloque chave `service_role` ou chave secreta no site público. Só uma chave publishable/anon pode aparecer no frontend, com RLS corretamente configurado.

## Arquivos
- `index.html` — aplicação completa nesta versão.
- `.nojekyll` — evita processamento desnecessário pelo Jekyll no GitHub Pages.


## Ajustes de correção
- Leitura numérica compatível com formatos brasileiros (ex.: R$ 1.234,56).
- Painel calcula receita/lucro com fallback para quantidade × valor unitário quando campos totais estiverem vazios.
- Importação reconhece nomes de abas e cabeçalhos ignorando acentos, espaços e pontuação.
- Importação preserva valores numéricos do Excel.

Antes de publicar, mantenha um backup dos dados locais. Esta versão continua usando armazenamento local do navegador; não sincroniza com Supabase.
