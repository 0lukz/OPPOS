# OPPOS

Sistema web de **ordens de serviço** para assistências técnicas. Permite cadastrar clientes, aparelhos, peças e serviços, acompanhar o andamento de cada conserto e enviar ao cliente um link para ele ver a própria ordem.

O OPPOS roda direto no navegador, no computador ou no celular, sem instalar nada.

## O que o sistema faz

- **Ordens de serviço**: cadastro com cliente, aparelho, problema relatado, peças, serviços, técnico, garantia, datas e observações.
- **Status da ordem**: Em aberto, Aguardando aprovação, Aguardando peça, Pronto para retirada, Entregue e Sem conserto.
- **Filtros**: por estado, tipo de aparelho e busca por nome, modelo, número de série ou número da OS.
- **Cadastros**: clientes, técnicos, peças e serviços, com preços. Ao criar uma ordem, os dados cadastrados aparecem como opção e preenchem os campos.
- **Totais automáticos**: total de peças, total de serviços e total da ordem.
- **Folha da ordem e PDF**: modelo pronto para imprimir ou baixar em PDF.
- **WhatsApp**: envia ao cliente uma mensagem com status, valor e previsão de entrega, junto com um link da ordem.
- **Link por ordem**: cada ordem gera o seu próprio link. O cliente abre a ordem numa página parecida com um PDF, e o conteúdo se atualiza quando a assistência altera a ordem. O link não mostra CPF, e-mail, telefone nem endereço do cliente.
- **Contas**: cada usuário cria a sua conta, com e-mail e senha, e tem o seu próprio banco de dados. Há opção "Manter conectado", "Esqueci minha senha", troca de senha e exclusão da conta.
- **Personalização**: cada conta define o nome da empresa, o CNPJ, o telefone e o endereço, que aparecem nas folhas e nas mensagens.

## Tecnologias

- HTML, CSS e JavaScript, sem framework.
- **Firebase Authentication** para login e cadastro.
- **Cloud Firestore** para o banco de dados.
- **GitHub Pages** para hospedar o site.
- **jsPDF** para gerar o PDF da ordem.

## Estrutura do projeto

- `index.html`: o sistema, com login, ordens e cadastros.
- `os.html`: a página que o cliente abre pelo link da ordem.
- `firebase-config.js`: as chaves do projeto Firebase.
- `firestore.rules`: as regras de segurança do banco de dados.

## Segurança

- Cada conta lê e grava só os próprios dados. As regras em `firestore.rules` bloqueiam o acesso às informações de outras contas.
- O link da ordem usa um código longo e aleatório. Só quem recebe o link consegue abrir aquela ordem, e ninguém consegue listar os links.
- As chaves em `firebase-config.js` identificam o projeto e não são secretas. A proteção vem das regras do Firestore e, se desejar, da restrição da chave por site no Google Cloud.
