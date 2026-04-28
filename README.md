# INTEL · Dashboard de Perfis WhatsApp

Dashboard de inteligência para análise de fotos de perfil do WhatsApp em lote.

---

## ⚠️ AVISO IMPORTANTE

Esta ferramenta usa a biblioteca **Baileys** (não-oficial).
- Viola os Termos de Serviço do WhatsApp
- O número usado como "ponte" pode ser **banido**
- Use um número descartável, não o seu número principal
- O uso é de inteira responsabilidade do operador

---

## Pré-requisitos

- **Node.js** versão 18 ou superior
- Download: https://nodejs.org

---

## Instalação

### 1. Extraia os arquivos
Coloque a pasta `whatsapp-intel` em qualquer local do seu computador.

### 2. Abra o terminal na pasta do projeto
```
cd caminho/para/whatsapp-intel
```

### 3. Instale as dependências
```
npm install
```
*(pode demorar 1-2 minutos na primeira vez)*

### 4. Inicie o servidor
```
npm start
```

### 5. Abra o dashboard no navegador
```
http://localhost:3000
```

---

## Como usar

### Passo 1 — Conectar o WhatsApp
1. Clique no botão **DESCONECTADO** no canto superior direito
2. Um QR Code aparecerá na tela
3. No celular: WhatsApp → Menu → Dispositivos conectados → Conectar dispositivo
4. Escaneie o QR Code
5. Aguarde a mensagem **CONECTADO**

### Passo 2 — Inserir os números
- Cole a lista de números na caixa lateral esquerda
- Um número por linha, no formato: `+5527996572965`

### Passo 3 — Buscar fotos
- Clique em **BUSCAR FOTOS DE PERFIL**
- As fotos serão carregadas automaticamente em lote
- A barra de progresso mostra o andamento
- Contas sem foto ou inexistentes serão marcadas como "S/ FOTO"

### Passo 4 — Analisar
- Clique em qualquer card para abrir os detalhes
- Classifique cada perfil: Anônima / Pública / Identificável
- Use ⚑ para marcar perfis relevantes
- Filtre por categoria usando os botões da barra superior

### Passo 5 — Exportar
- Clique em **EXPORTAR RELATÓRIO** para salvar um `.txt` com todos os dados

---

## Estrutura do projeto

```
whatsapp-intel/
├── server/
│   └── index.js        ← Servidor Node.js + integração Baileys
├── public/
│   └── index.html      ← Dashboard frontend
├── auth_info/          ← Criada automaticamente (sessão WhatsApp)
├── package.json
└── README.md
```

---

## Notas técnicas

- A pasta `auth_info/` é criada automaticamente após o primeiro login
- A sessão é mantida entre reinicializações (não precisa escanear QR toda vez)
- Para deslogar: delete a pasta `auth_info/` e reinicie o servidor
- Um delay de ~800ms-1500ms é aplicado entre cada consulta para reduzir risco de detecção
