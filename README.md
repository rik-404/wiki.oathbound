# Wiki do Oathbound

Site estático independente, preparado para publicação em `https://wiki.jogue-oathbound.online/`.

## Publicação e domínio

Publique **o conteúdo desta pasta** em uma hospedagem de sites estáticos. Na hospedagem, adicione `wiki.jogue-oathbound.online` como domínio personalizado e configure no DNS o registro indicado por ela (normalmente um CNAME para `wiki`). Isso mantém o site do jogo no domínio atual.

## Banco e permissões

1. Confirme que `supabase/admin-panel.sql` já foi executado e que sua conta está na lista de Devs do jogo.
2. Execute `supabase/admin-wiki.sql` uma vez no SQL Editor do mesmo projeto Supabase.
3. Em Supabase → Authentication → URL Configuration, adicione `https://wiki.jogue-oathbound.online/` à lista de Redirect URLs. Para prévia local, adicione também o endereço local exato usado pelo servidor de desenvolvimento.
4. Configure o login OAuth do Discord no Supabase, se ainda não estiver ativo.
5. Abra a Wiki, selecione **Entrar como Dev** e autentique com a conta Dev. O botão **Novo artigo** e a opção **Editar artigo** aparecem para contas autorizadas.

As páginas iniciais ficam em `seed.json`. Edições feitas pelo painel são gravadas no Supabase e passam a aparecer aos visitantes sem republicar a Wiki. Páginas em rascunho só são visíveis às contas Dev. A tabela de índice pública contém apenas o estado de publicação e remoção, nunca o texto de rascunhos.

## Prévia local

Sirva esta pasta por HTTP para que `seed.json`, imagens e o login OAuth funcionem; não abra `index.html` diretamente por `file://`. Exemplo com Python instalado: `python -m http.server 5500` executado dentro desta pasta e abra `http://localhost:5500/`.
