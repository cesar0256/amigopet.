# AmigoPet: versão de teste para enviar aos amigos

Esta pasta é o app instalável (PWA). Para os amigos instalarem, ela precisa ficar num endereço **https**. O jeito mais rápido é o Netlify Drop, que é gratuito e não exige programação.

## Publicar em 2 minutos (Netlify Drop)

1. Entre em https://app.netlify.com/drop (crie uma conta gratuita se pedir).
2. Arraste a **pasta inteira** `amigopet-teste` (ou o arquivo `.zip`) para a página.
3. Em segundos o Netlify mostra um endereço parecido com `https://nome-aleatorio.netlify.app`. Esse é o link do teste.
4. Opcional: em *Site configuration > Change site name*, escolha um nome como `amigopet-teste`.
5. Abra o link no seu celular para conferir antes de enviar.

Alternativas: GitHub Pages, Vercel ou Cloudflare Pages funcionam do mesmo jeito.

## O que mandar para os amigos

> Oi! Estou testando um app de cuidados para pets, o AmigoPet. Abra este link no celular: **(seu link)**
> No Android use o Chrome, e no iPhone use o Safari. Depois entre em **Menu > Instalar** para colocar o app na tela inicial.
> Siga o roteiro em **Menu > Teste** e me mande o seu feedback por lá. Obrigado! 🐾

## Receber o feedback pelo seu WhatsApp (opcional)

Por padrão, o botão "Enviar feedback" abre o compartilhamento do celular do amigo. Para as mensagens chegarem direto no seu WhatsApp, abra `index.html` num editor de texto, procure `FEEDBACK_WA=''` e coloque seu número com DDI e DDD, sem símbolos:

```
FEEDBACK_WA='5547999999999'
```

## Como o teste funciona

- Cada amigo tem o **seu próprio app e os seus próprios dados**, guardados só no celular dele. Ninguém vê os dados de ninguém, e você também não vê.
- Na primeira abertura aparece uma mensagem de boas-vindas com a opção de carregar dados de demonstração.
- O app funciona sem internet depois de aberto uma vez.
- Se o amigo limpar os dados do navegador ou desinstalar o app, os dados dele somem. Há "Exportar backup" em Ajustes.

## Publicar uma nova versão

1. Troque o `index.html` pelo novo.
2. Em `sw.js`, mude o número em `const V = 'amigopet-teste-0.1'` (por exemplo para `0.2`).
3. Arraste a pasta de novo no Netlify (no site existente, em *Deploys*).

Quem abrir o app com internet recebe a versão nova.

## Observações

- **Instalação no iPhone:** só funciona pelo Safari, em *Compartilhar > Adicionar à Tela de Início*. O botão "Instalar agora" não existe no iOS.
- **GPS do passeio:** funciona só em https, e o navegador pede permissão.
- **Dados de saúde dos pets:** para o lançamento oficial, publique Termos de uso e Política de privacidade.
- **Versão com login e sincronização:** continua na pasta `amigopet-supabase`, para quando você quiser vários aparelhos compartilhando os mesmos dados.
