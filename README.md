# 🌧️ Alerta Jundiaí

Aplicativo desenvolvido para registrar e acompanhar ocorrências de alagamentos no município de Jundiaí-SP.

## 🛠️ Pré-requisitos

Antes de começar, certifique-se de que possui os seguintes programas instalados no computador:

1. **Node.js** (https://nodejs.org/pt-br).
2. **PostgreSQL e pgAdmin** (https://www.postgresql.org/).
3. **Flutter SDK** (https://docs.flutter.dev/install/archive).
4. **Android Studio:** https://developer.android.com/studio?hl=pt-br

---

## Passo 1: Preparar o Banco de Dados

1. Abra o pgAdmin e conecte-se utilizando sua senha do PostgreSQL.
2. Crie um novo banco de dados chamado `alerta_jundiai`.
3. Selecione o banco `alerta_jundiai` e acesse **Tools (Ferramentas) → Query Tool**.
4. Cole o script SQL abaixo e clique no botão de executar (Play) para criar a tabela de ocorrências.

```sql
CREATE TABLE alagamentos (
    id SERIAL PRIMARY KEY,
    latitude DECIMAL(10, 7) NOT NULL,
    longitude DECIMAL(10, 7) NOT NULL,
    gravidade VARCHAR(20) NOT NULL,
    descricao TEXT,
    data_criacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## Passo 2: Configurar as Credenciais da API

1. Extraia o projeto recebido e abra a pasta raiz `alerta-jundiai-api`.
2. Localize o arquivo chamado `.env` e abra-o com qualquer editor de texto, como Bloco de Notas ou VS Code.
3. Altere o valor de `DB_PASSWORD` para a senha do PostgreSQL instalada no seu computador.
4. Salve o arquivo. O conteúdo deverá ficar parecido com este:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=sua_senha_aqui
DB_NAME=alerta_jundiai
PORT=3000
```

**Atenção:** Substitua `sua_senha_aqui` pela sua senha real do PostgreSQL.

---

## Passo 3: Instalar as Dependências

Caso a pasta `node_modules` não esteja presente no projeto, será necessário instalar os pacotes necessários (Express, CORS, PG, entre outros).

1. Abra o Terminal, Prompt de Comando ou PowerShell dentro da pasta `Alerta_Jundiai`.
2. Digite o seguinte comando e pressione Enter:

```bash
npm install
```

3. Aguarde até que a instalação das dependências seja concluída.

---

## Passo 4: Iniciar o Servidor (Backend)

1. No mesmo terminal, inicie a API utilizando um dos comandos abaixo:

```bash
npm run dev
```

Ou:

```bash
npm start
```

2. Aguarde a inicialização. A seguinte mensagem deverá aparecer indicando que a conexão com o banco de dados foi realizada:

```text
Conexão com PostgreSQL realizada com sucesso!
```

**⚠️ Atenção:** Não feche esse terminal! Ele precisa permanecer aberto para que a API continue funcionando.

---

## Passo 5: Abrir o Aplicativo (Frontend)

1. Abra o Android Studio.
2. Abra o projeto Flutter no Android Studio.
3. Acesse o **Device Manager** e inicie um emulador Android.
4. Após iniciar o emulador, abra o CMD ou PowerShell na pasta raiz do projeto Flutter.
5. Execute o seguinte comando:

```bash
flutter run
```

O Flutter começará a compilar e instalar o aplicativo no emulador. Após a conclusão, o Alerta Jundiaí será aberto automaticamente.

---

## ✅ Conclusão

Após concluir todas as etapas, o ambiente estará configurado e o aplicativo Alerta Jundiaí estará pronto para utilização.

**Importante:** Para o funcionamento completo do sistema, mantenha o servidor Backend (API) em execução enquanto utiliza o aplicativo.
