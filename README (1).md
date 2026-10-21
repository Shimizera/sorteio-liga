# Sorteio da Liga

Site de sorteio para posts do Instagram da liga. Puxa os comentários pela API oficial da Meta, confere as regras (marcações mínimas, palavra obrigatória, excluídos), sorteia com gerador aleatório criptográfico e ajuda a conferir se o ganhador segue os perfis exigidos.

Tudo roda no navegador. Não há servidor nem banco de dados: o token fica só no computador de quem usa.

## O que dá e o que não dá para conferir sozinho

| Regra | Conferência |
|---|---|
| Marcar N pessoas diferentes | Automática (não conta quem marca a si mesmo, a própria liga nem marcação repetida) |
| Palavra obrigatória no comentário | Automática |
| Excluir organizadores | Automática |
| Seguir perfis | **Manual, só no ganhador.** A API do Instagram não informa quem segue quem. A página mostra caixinhas e o link do perfil para checar; se não segue, "Desclassificar e sortear outro". Os sites de sorteio pagos fazem igual ou estimam. |

## Configuração (uma vez só, ~20 min)

### 1. Conta da liga precisa ser profissional
No app do Instagram: Configurações → Tipo de conta e ferramentas → mudar para conta profissional (Criador de conteúdo ou Empresa). É grátis.

### 2. Criar o app na Meta e gerar o token
1. Entre em https://developers.facebook.com com uma conta do Facebook e crie um app.
2. No caso de uso, escolha o de gerenciar mensagens e conteúdo no Instagram (a "API do Instagram com login do Instagram").
3. Em funções do app, adicione a conta da liga como **testador do Instagram**. Aceite o convite no Instagram em Configurações → Apps e sites → Convites de teste.
4. Na tela de configuração da API, clique em gerar token para a conta da liga, autorizando as permissões `instagram_business_basic` e `instagram_business_manage_comments`.
5. Copie o token (começa com `IG`). Ele vale cerca de 60 dias; depois é só gerar outro.

O app pode ficar em modo de desenvolvimento: como só a conta da própria liga usa, não precisa passar por revisão da Meta.

**Não compartilhe o token.** Quem tiver ele consegue ler e responder comentários da conta.

### 3. Publicar no GitHub Pages
1. Crie um repositório no GitHub (ex.: `sorteio-liga`) e envie o `index.html` (botão "Add file → Upload files").
2. Settings → Pages → Branch `main`, pasta `/ (root)` → Save.
3. Em alguns minutos o site fica em `https://SEU-USUARIO.github.io/sorteio-liga/`.

## Usando
1. Abra o site, cole o token e clique em **Ver posts** (ou cole o link do post).
2. Clique no post do sorteio. Os comentários são puxados (50 por vez, até o fim).
3. Ajuste as regras e veja quem ficou fora e por quê.
4. Clique em **Sortear**. Confira se o ganhador segue os perfis, confirme ou desclassifique.
5. **Copiar resultado** gera o texto para anunciar. Grave a tela durante o sorteio para dar transparência.

Se a API der problema no dia, a aba **Colar manualmente** aceita comentários copiados do Instagram ou um CSV.
