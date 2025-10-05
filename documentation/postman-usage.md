# 📚 Guia de Uso do Postman - Coleções ServeRest

## 🚀 Pré-requisitos

### 📦 Servidor Local Obrigatório
Antes de usar as collections, inicie o servidor ServeRest localmente:

```bash
npx serverest@latest
```

O servidor será executado em `http://localhost:3000`

## 📥 Importação das Coleções

### 1. Download dos Arquivos
```bash
# Clone o repositório
git clone https://github.com/gabrielroquim/apiTesting.git

# Arquivos necessários:
# - collections/exploratory-tests/testesExploratorios.json
# - environments/ServeRest-DEV.postman_environment.json
```

### 2. Importação no Postman
1. Abra o Postman
2. Clique em **Import** (canto superior esquerdo)
3. Arraste os arquivos `.json` ou clique em **Upload Files**
4. Selecione os arquivos:
   - Coleção: `testesExploratorios.json`
   - Environment: `ServeRest-DEV.postman_environment.json`
5. Clique em **Import**

## ⚙️ Configuração do Environment

### Seleção do Environment
1. No canto superior direito, clique no dropdown de environments
2. Selecione **ServeRest - DEV Environment (Local)**
3. Verifique se a variável `baseUrl` está definida como `http://localhost:3000`

### Variáveis da Collection Atual
```javascript
// Variáveis configuradas na collection
idUsuario: "" // ID do usuário criado (preenchido automaticamente)
administrador: "true" // Tipo de usuário padrão
baseUrl: "http://localhost:3000" // Servidor local
```

### Variáveis Dinâmicas Geradas
```javascript
// Geradas automaticamente nos pre-request scripts
nomeUsuario: "gandalf_XXXX" // Nome único
senhaUsuario: "senhaXXXX" // Senha única
emailUsuario: "mago_cor@hobbit.org" // Email com cor aleatória
```

## 🎮 Executando os Testes

### 1. Execução Manual (Request por Request)

#### Para Testes Individuais:
1. Expanda a coleção **Testes Exploratórios**
2. Selecione uma requisição específica
3. Clique em **Send**
4. Analise a resposta na aba **Body**
5. Verifique os testes na aba **Test Results**

#### Exemplo - Criar Usuário:
```javascript
// Script Pré-requisição (automático)
pm.environment.set("userEmail", `usuario${Date.now()}@teste.com`);
pm.environment.set("userPassword", "senha123");

// Corpo da Requisição (automático)
{
  "nome": "Usuario Teste",
  "email": "{{userEmail}}",
  "password": "{{userPassword}}",
  "administrador": "true"
}

// Testes (automático)
pm.test("Status deve ser 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Deve retornar ID do usuário", function () {
    const response = pm.response.json();
    pm.expect(response._id).to.be.a('string');
    pm.environment.set("userId", response._id);
});
```

### 2. Execução em Lote (Collection Runner)

#### Via Interface Gráfica:
1. Clique com botão direito na coleção
2. Selecione **Run collection**
3. Configure as opções:
   - **Iterations:** 1 (para teste básico)
   - **Delay:** 1000ms (entre requisições)
   - **Data file:** Nenhum (usar dados automáticos)
4. Clique em **Run Testes Exploratórios**

#### Configurações Recomendadas:
- ✅ **Save responses:** Para debug
- ✅ **Keep variable values:** Para manter dados entre iterações
- ✅ **Run collection without using stored cookies:** Para testes limpos
- ⚠️ **Delay:** 500-1000ms para não sobrecarregar a API

### 3. Execução via Newman (CLI)

#### Instalação:
```bash
npm install -g newman
npm install -g newman-reporter-html
```

#### Execução Básica:
```bash
newman run collections/exploratory-tests/testesExploratorios.json \
  -e environments/ServeRest-DEV.postman_environment.json \
  --delay-request 1000
```

#### Com Relatórios:
```bash
newman run collections/exploratory-tests/testesExploratorios.json \
  -e environments/ServeRest-DEV.postman_environment.json \
  --reporters html,cli \
  --reporter-html-export results/report.html \
  --delay-request 1000
```

## 📊 Interpretando os Resultados

### Status dos Testes
- 🟢 **Pass:** Teste passou com sucesso
- 🔴 **Fail:** Teste falhou - requer investigação
- ⚪ **Skip:** Teste foi pulado (condicional)

### Métricas Importantes
```javascript
// Exemplo de resultado
Collection: Testes Exploratórios
Requests: 15/15 passed
Test Scripts: 45/45 passed
Assertions: 45/45 passed
Average Response Time: 234ms
```

### Interpretação de Falhas
```javascript
// Exemplo de falha comum
❌ Status deve ser 200
   AssertionError: expected 500 to equal 200
   
// Ação: Verificar se a API está funcionando
// Verificar se os dados enviados estão corretos
```

## 🔧 Personalização e Extensão

### Adicionando Novos Testes
```javascript
// Template para novos testes
pm.test("Descrição do teste", function () {
    // Sua validação aqui
    pm.response.to.have.status(200);
    
    const response = pm.response.json();
    pm.expect(response.property).to.equal("expected_value");
});
```

### Scripts Úteis

#### Pre-request Script para Dados Aleatórios:
```javascript
// Gerar email único
const timestamp = Date.now();
pm.environment.set("randomEmail", `user${timestamp}@test.com`);

// Gerar nome aleatório
const names = ["João", "Maria", "Pedro", "Ana"];
const randomName = names[Math.floor(Math.random() * names.length)];
pm.environment.set("randomName", randomName);
```

#### Test Script para Salvar Dados:
```javascript
// Salvar ID da resposta
if (pm.response.code === 201) {
    const response = pm.response.json();
    pm.environment.set("createdId", response._id);
}

// Validar schema da resposta
const schema = {
    type: "object",
    properties: {
        _id: { type: "string" },
        nome: { type: "string" },
        email: { type: "string" }
    },
    required: ["_id", "nome", "email"]
};

pm.test("Schema validation", function() {
    pm.response.to.have.jsonSchema(schema);
});
```

## 🐛 Troubleshooting

### Problemas Comuns

#### 1. Environment não selecionado
**Sintoma:** Variáveis `{{baseUrl}}` aparecem literalmente
**Solução:** Selecionar o environment correto no dropdown

#### 2. Token expirado
**Sintoma:** Erro 401 em requests autenticados
**Solução:** Executar novamente o request de login

#### 3. API indisponível
**Sintoma:** Timeout ou erro de conexão
**Solução:** Verificar https://serverest.dev no browser

#### 4. Dados duplicados
**Sintoma:** Erro 400 "Email já cadastrado"
**Solução:** Usar dados aleatórios nos pre-request scripts

### Debug Tips
```javascript
// Adicionar no Test Script para debug
console.log("Response:", pm.response.json());
console.log("Status:", pm.response.code);
console.log("Headers:", pm.response.headers.all());
```

## 📈 Boas Práticas

### Organização
- ✅ Use nomes descritivos para requests
- ✅ Agrupe requests relacionados em folders
- ✅ Documente cada request na aba Description
- ✅ Use variáveis para todos os dados dinâmicos

### Performance
- ✅ Configure delays apropriados (500-1000ms)
- ✅ Evite loops infinitos em testes
- ✅ Use cleanup scripts para limpar dados
- ✅ Monitore o tempo de resposta

### Manutenção
- ✅ Mantenha collections atualizadas
- ✅ Revise testes regularmente
- ✅ Documente mudanças importantes
- ✅ Use versionamento para collections críticas

## 🔄 Próximos Passos

1. **Executar Testes Exploratórios:** Familiarize-se com a collection básica
2. **Newman CLI:** Configure execução via linha de comando
3. **CI/CD:** Integre com GitHub Actions (futuro)
4. **Collections Avançadas:** Aguarde releases das próximas collections

---

**💡 Dicas:** Sempre execute os testes em ambiente de desenvolvimento primeiro!  
**📞 Suporte:** Abra uma issue no GitHub para dúvidas específicas.
