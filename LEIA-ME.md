# AmigoPet: pacote de produção

Esta pasta é o app final. Hospede os arquivos no seu domínio, com **https**.

## Antes de publicar (obrigatório)

1. Abra `legal-config.js` num editor de texto e preencha os dados da sua empresa: nome, CNPJ, e-mail de contato, plataforma de pagamento e encarregado de dados (DPO). Esses dados aparecem no app e nas páginas de Termos e Privacidade.
2. Leia `termos.html` e `privacidade.html` no navegador e confira se o texto reflete o que você pratica. Pontos a confirmar:
   - **Cancelamento:** os Termos dizem que o plano mensal pode ser cancelado a qualquer momento e que o cancelamento impede novas cobranças.
   - **Reembolso:** os Termos citam 7 dias corridos, como na página de vendas.
   - **Preços:** R$ 5,00 por mês e R$ 27,00 por ano.
   - **Foro:** o domicílio do consumidor.
   - **Dados da plataforma:** a Política diz que a plataforma de pagamento e você tratam nome, e-mail e documento fiscal. Ajuste se coletar outros dados.
3. **Peça a revisão de um advogado**, de preferência com experiência em LGPD. Os textos foram escritos com base no que o app faz hoje, mas são um modelo e não substituem a análise jurídica.

## Publicar

1. Envie **todos os arquivos** desta pasta para a raiz do seu site. O `index.html` deve ficar na raiz.
2. Abra o endereço no celular e confira: tela de carregamento, aceite dos Termos, cadastro de um pet e a aba **Instalar**.
3. Na sua página de vendas e na plataforma de pagamento, use estes links:
   - Termos de Uso: `https://seudominio.com.br/termos.html`
   - Política de Privacidade: `https://seudominio.com.br/privacidade.html`

## O que mudou em relação à versão de teste

- Saíram a aba **Teste** e a mensagem de fase de testes.
- Entrou a aba **Termos e privacidade**, com Termos de Uso, Política de Privacidade e direitos da LGPD, mais os botões **Exportar meus dados** e **Apagar todos os dados**.
- Na primeira abertura, o app pede o aceite dos Termos e da Política. O aceite fica registrado no aparelho, e quando você mudar `VERSAO` em `legal-config.js` o app pede um novo aceite.
- A aba **Ajustes** foi removida: backup, importar, apagar dados, demonstração, assinatura e suporte agora ficam na aba **Termos e privacidade**.

## Atualizar o app depois

1. Substitua o `index.html` (e os outros arquivos alterados).
2. Em `sw.js`, mude o número em `const V = 'amigopet-1.0.2'` (por exemplo, para `1.0.3`). Assim os celulares pegam a versão nova.

## Importante saber

- **Acesso:** o app não sabe quem pagou. Quem tiver o link consegue usar. Se isso for um problema, o próximo passo é a versão com contas e pagamento automático (pasta `amigopet-supabase`).
- **Dados dos usuários:** ficam só no aparelho de cada um, e você não tem acesso a eles. A Política já diz isso. Se você passar a coletar dados (login, estatísticas, mapas, anúncios), **atualize os textos antes**.
- **Google Fonts:** a fonte do app é carregada dos servidores do Google, que recebe o IP do usuário. A Política já informa isso. Se quiser evitar, hospede as fontes você mesmo.
- **Mapa do passeio:** hoje é desenhado sobre uma grade, sem mapa de ruas. Se adicionar um provedor de mapas, inclua na Política.
- **iPhone:** a instalação só funciona pelo Safari, e as notificações só com o app instalado na tela inicial.
