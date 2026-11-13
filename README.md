# OPPOS — Ordens de Serviço

Sistema de ordens de serviço para assistência técnica. Site estático (GitHub Pages) com login e banco de dados no Firebase (plano gratuito).

## Passo a passo (cerca de 20 minutos)

### 1. Criar o projeto no Firebase
1. Acesse https://console.firebase.google.com e entre com sua conta Google.
2. Clique em **Criar projeto**, dê o nome **oppos** e siga até o fim. Pode desativar o Google Analytics.

### 2. Ativar o login por e-mail e senha
1. No menu da esquerda: **Criação > Authentication > Vamos começar**.
2. Aba **Método de login > E-mail/senha > Ativar > Salvar**.

### 3. Criar o banco de dados
1. No menu: **Criação > Firestore Database > Criar banco de dados**.
2. Local: **southamerica-east1 (São Paulo)**. Modo: **produção**.
3. Abra a aba **Regras**, apague o que estiver lá, cole o conteúdo do arquivo `firestore.rules` e clique em **Publicar**.

### 4. Pegar as chaves e colar no site
1. Engrenagem ao lado de **Visão geral do projeto > Configurações do projeto**.
2. Em **Seus apps**, clique no ícone **</>** (Web), dê o apelido **oppos** e registre o app.
3. Copie os valores de `firebaseConfig` e cole em `firebase-config.js`, trocando só o que está entre aspas.

### 5. Publicar no GitHub
1. Em https://github.com/new crie o repositório **OPPOS**. Marque **Public** (o GitHub Pages gratuito exige repositório público).
2. Clique em **uploading an existing file** e envie `index.html` e `firebase-config.js`. Os outros arquivos são opcionais. Clique em **Commit changes**.
3. **Settings > Pages > Build and deployment > Source: Deploy from a branch**. Branch **main**, pasta **/ (root)**. Salve.
4. Em 1 a 2 minutos o endereço aparece: `https://SEU-USUARIO.github.io/OPPOS/`.

### 6. Autorizar o endereço no Firebase
1. Firebase > **Authentication > Configurações > Domínios autorizados > Adicionar domínio**.
2. Adicione `SEU-USUARIO.github.io`.

Pronto. Abra o endereço, clique em **Criar conta** e use o sistema.

## Observações
- As chaves em `firebase-config.js` ficam visíveis a quem abrir o site. Isso é normal no Firebase. Quem protege os dados são as regras do passo 3.
- Cada conta vê só as próprias ordens, clientes, técnicos, peças e serviços.
- Limite gratuito do Firebase (Spark): 1 GiB de dados, 50 mil leituras e 20 mil gravações por dia. Cada vez que o sistema abre, ele lê todos os cadastros da conta.
- "Esqueci minha senha" envia um e-mail de redefinição pelo Firebase.
- Os dados do sistema antigo (claude.ai) não vêm sozinhos para cá. Refaça os cadastros, ou peça ajuda para exportar.
