# 🔍 Testes Exploratórios - API ServeRest

## 🚀 Pré-requisitos

### 📦 Inicializando o Servidor Local
Antes de executar os testes, você precisa iniciar o servidor ServeRest localmente:

```bash
npx serverest@latest
```

O servidor será iniciado em `http://localhost:3000`

### ⚙️ Configuração da Collection
- **Base URL:** `http://localhost:3000`
- **Environment:** ServeRest-DEV (configure com a baseUrl correta)
- **Variáveis:** A collection usa variáveis dinâmicas para gerar dados únicos

## 📊 Cobertura de Testes

### 👤 Usuários (/usuarios) - CRUD Completo
- ✅ **Cadastrar usuários** - POST /usuarios
  - Gera dados aleatórios (nome como "gandalf_XXXX", email com paleta de cores)
  - Valida status 201 e mensagem de sucesso
  - Salva ID do usuário criado
- ✅ **Buscar usuário por ID** - GET /usuarios/{id}
  - Valida status 200
  - Verifica se o perfil é administrador
- ✅ **Atualizar usuário** - PUT /usuarios/{id}
  - Usa dados aleatórios do Postman ($randomFirstName, $randomEmail)
  - Valida status 201 e mensagem "Registro alterado com sucesso"
- ✅ **Listar usuários** - GET /usuarios
  - Valida status 200
  - Verifica campos obrigatórios (nome, email, password, administrador)
- ✅ **Deletar usuário por ID** - DELETE /usuarios/{id}
  - Valida mensagem "Registro excluído com sucesso"

## 🔄 Fluxo de Execução
A collection executa um CRUD completo de usuários:
1. **Cadastra** um usuário com dados únicos
2. **Busca** o usuário criado por ID
3. **Atualiza** os dados do usuário
4. **Lista** todos os usuários
5. **Deleta** o usuário criado

## 🧪 Funcionalidades de Teste

### 🎲 Geração Dinâmica de Dados
- **Nomes:** `gandalf_` + número aleatório (0-9999)
- **Senhas:** `senha` + número aleatório (0-9999)
- **Emails:** `mago_` + cor aleatória + `@hobbit.org`
- **Paleta de cores:** 25+ cores diferentes para emails únicos

### ✅ Validações Implementadas
- Status codes (200, 201, 400)
- Mensagens de resposta específicas
- Campos obrigatórios nas respostas
- Persistência de dados (ID do usuário entre requests)

### 📝 Cenários de Teste
- ✅ Casos de sucesso (201 Created, 200 OK)
- ✅ Casos de erro (400 Bad Request - email duplicado, email inválido)
- ✅ Responses de exemplo documentados
- ✅ Validação de campos obrigatórios

## 🔧 Configuração Técnica

### Variáveis da Collection
```json
{
  "idUsuario": "",
  "administrador": "true",
  "baseUrl": "http://localhost:3000"
}
```

### Pre-request Scripts
- Geração automática de nomes únicos
- Criação de emails com paleta de cores aleatória
- Configuração de senhas dinâmicas

### Test Scripts
- Validação de status codes específicos
- Verificação de mensagens de resposta
- Salvamento de IDs para uso posterior
- Verificação de campos obrigatórios

## 📈 Métricas Esperadas

- **Taxa de Sucesso:** 100% (quando servidor local está rodando)
- **Tempo de Resposta:** < 100ms (servidor local)
- **Cobertura:** CRUD completo de usuários
- **Validações:** 15+ testes automatizados

## 🚨 Requisitos Importantes

1. **Servidor Local Obrigatório:** Execute `npx serverest@latest` antes dos testes
2. **Base URL:** Deve estar configurada como `http://localhost:3000`
3. **Environment:** Use ServeRest-DEV com configuração local

## 📝 Observações

- Collection completamente independente
- Não requer autenticação prévia
- Dados são criados e removidos automaticamente
- Pode ser executada repetidamente sem conflitos
- Focada em testes exploratórios do endpoint /usuarios

## 🔄 Próximos Passos

1. Expandir para outros endpoints (produtos, login, carrinhos)
2. Adicionar testes de cenários negativos
3. Implementar validações de schema JSON
4. Adicionar testes de performance

---

**Criado por:** Gabriel  
**Data:** Outubro 2025  
**Foco:** CRUD completo de usuários com dados dinâmicos  
**LinkedIn:** [Post sobre testes exploratórios](#)
