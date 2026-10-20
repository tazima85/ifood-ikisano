# ifood-ikisano

Painel estático (uma única página HTML) para chamar as ações da Edge Function
`ifood-pausas` (projeto Supabase "Reports Boali") sem precisar de `curl`. Pensado
para crescer com novas chamadas às APIs do iFood das lojas, conforme necessário.

Não contém nenhum segredo: o login é feito com email/senha reais via Supabase Auth,
validados pela própria Edge Function a cada chamada. A `anon key` embutida no
`index.html` não é um segredo — é a chave pública do projeto, feita para ficar em
código de front-end.

## Pré-requisito: criar o usuário de login

No Dashboard do Supabase do projeto ("Reports Boali") → **Authentication → Users →
Add user**, crie um usuário com seu email e uma senha — é esse login que o painel vai
usar.

## Hospedagem (GitHub Pages)

Settings → Pages → Source: **Deploy from a branch** → branch `main`, pasta `/ (root)`.
Depois disso a página fica disponível em `https://tazima85.github.io/ifood-ikisano/`.

## Uso

Abra a URL do Pages, entre com seu email/senha, e use os botões para chamar cada ação
(listar lojas, consultar status, criar/listar/remover pausa, configurar horário,
enviar teste de WhatsApp, rodar o monitoramento manualmente). O resultado de cada
chamada aparece na área de saída, com histórico das últimas 20 chamadas.
