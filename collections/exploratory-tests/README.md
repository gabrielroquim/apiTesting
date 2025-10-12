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

### 🔐 Autenticação
- ✅ **Login Padrão** - POST /login
  - Valida credenciais com usuário padrão (fulano@qa.com)
  - Verifica status 200 para autenticação bem-sucedida
  - Base para fluxos que requerem autenticação

### 👤 Usuários (/usuarios) - CRUD Completo
- ✅ **Cadastrar usuários** - POST /usuarios
  - **Geração inteligente de dados** com configurações centralizadas
  - **Senhas seguras** com caracteres especiais e comprimento mínimo
  - **Emails únicos** usando timestamp para evitar duplicatas
  - **Logs detalhados** para rastreabilidade com mascaramento de senhas
  - Valida status 201 e mensagem de sucesso
  - Salva ID do usuário criado automaticamente
- ✅ **Buscar usuário por ID** - GET /usuarios/{id}
  - Valida status 200
  - Verifica se o perfil é administrador
- ✅ **Atualizar usuário** - PUT /usuarios/{id}
  - Usa dados aleatórios do Postman ($randomFirstName, $randomEmail)
  - Valida status 200 e mensagem "Registro alterado com sucesso"
- ✅ **Listar usuários** - GET /usuarios
  - Valida status 200
  - Verifica campos obrigatórios (nome, email, password, administrador)
  - Documentação completa do endpoint com exemplos
- ✅ **Deletar usuário por ID** - DELETE /usuarios/{id}
  - Valida mensagem "Registro excluído com sucesso"
  - Documentação detalhada do processo de exclusão

## 🔄 Fluxo de Execução
A collection executa um fluxo completo de autenticação e CRUD de usuários:
1. **Login** com credenciais padrão para estabelecer sessão
2. **Cadastra** um usuário com dados únicos e seguros
3. **Busca** o usuário criado por ID
4. **Atualiza** os dados do usuário
5. **Lista** todos os usuários
6. **Deleta** o usuário criado

## 🧪 Funcionalidades de Teste

### 🎲 Geração Dinâmica de Dados
#### 🔧 Configurações Centralizadas
```javascript
const config = {
    prefixoUsuario: 'gandalf',
    dominio: 'cinzento.org',
    senhaMinLength: 8
};
```

#### 🎯 Padrões de Dados Gerados
- **Nomes:** `gandalf_` + número aleatório (0-9999)
- **Senhas Seguras:** String alfanumérica + `@` + número (mínimo 8 caracteres)
- **Emails Únicos:** `mago_` + cor aleatória + `_` + timestamp + `@cinzento.org`
- **Paleta de cores:** 25+ cores diferentes para garantir unicidade
- **Timestamp:** Uso de `Date.now()` para evitar duplicatas

#### 🔍 Logs e Rastreabilidade
- Console detalhado com dados gerados
- Mascaramento automático de senhas nos logs
- Armazenamento em environment variables para uso posterior
- Timestamp para auditoria

### ✅ Validações Implementadas
- **Status codes:** 200, 201, 400 com validações específicas
- **Mensagens de resposta:** Validação exata de textos esperados
- **Campos obrigatórios:** Verificação completa nas respostas JSON
- **Persistência de dados:** ID do usuário compartilhado entre requests
- **Autenticação:** Validação de login e perfis de usuário
- **Segurança:** Mascaramento de dados sensíveis nos logs

### 📝 Cenários de Teste
- ✅ **Login bem-sucedido** (200 OK)
- ✅ **Cadastros de sucesso** (201 Created)
- ✅ **Consultas efetivas** (200 OK)
- ✅ **Atualizações válidas** (200 OK)
- ✅ **Exclusões confirmadas** (200 OK)
- ✅ **Casos de erro documentados:**
  - 400 Bad Request - email duplicado
  - 400 Bad Request - email inválido
  - 400 Bad Request - administrador deve ser 'true' ou 'false'
- ✅ **Responses de exemplo** completos e atualizados
- ✅ **Documentação detalhada** de endpoints

## 🔧 Configuração Técnica

### Variáveis da Collection
```json
{
  "idUsuario": "",
  "administrador": "true"
}
```

### 🔧 Scripts Avançados

#### Pre-request Scripts
- **Configurações centralizadas** para facilitar manutenção
- **Geração automática** de nomes únicos com prefixo personalizado
- **Criação de emails únicos** usando timestamp para evitar conflitos
- **Senhas seguras** com caracteres especiais e validação de comprimento
- **Logs detalhados** com mascaramento de dados sensíveis
- **Paleta de cores dinâmica** com 25+ opções

#### Test Scripts
- **Validação rigorosa** de status codes específicos
- **Verificação exata** de mensagens de resposta
- **Salvamento automático** de IDs para uso posterior
- **Verificação completa** de campos obrigatórios
- **Validação de perfis** (administrador/usuário comum)

## 📈 Métricas Esperadas

- **Taxa de Sucesso:** 100% (quando servidor local está rodando)
- **Tempo de Resposta:** < 100ms (servidor local)
- **Cobertura:** Login + CRUD completo de usuários
- **Validações:** 20+ testes automatizados
- **Segurança:** Dados sensíveis mascarados nos logs
- **Unicidade:** 0% chance de conflito por email duplicado

## 🚨 Requisitos Importantes

1. **Servidor Local Obrigatório:** Execute `npx serverest@latest` antes dos testes
2. **Base URL:** Deve estar configurada como `http://localhost:3000`
3. **Environment:** Use ServeRest-DEV com configuração local

## 📝 Observações

- **Collection completamente independente** com dados auto-gerados
- **Login automatizado** para fluxos que requerem autenticação
- **Dados únicos garantidos** através de timestamp
- **Segurança aprimorada** com mascaramento de senhas
- **Logs detalhados** para debugging e auditoria
- **Configurações centralizadas** para fácil manutenção
- **Pode ser executada repetidamente** sem conflitos
- **Focada em testes exploratórios** dos endpoints de autenticação e usuários
- **Senhas robustas** seguindo boas práticas de segurança

## 🔄 Próximos Passos

1. **Expandir autenticação** para outros fluxos (tokens, refresh)
2. **Adicionar outros endpoints** (produtos, carrinhos, pedidos)
3. **Implementar testes de cenários negativos** avançados
4. **Validações de schema JSON** com bibliotecas especializadas
5. **Testes de performance** e carga
6. **Integração com CI/CD** para execução automatizada
7. **Relatórios detalhados** com métricas de performance

---

**Criado por:** Gabriel  
**Data:** Outubro 2025  
**Versão:** 2.0 - Atualização Completa  
**Foco:** Login + CRUD completo com dados seguros e únicos  
**Melhorias:** Logs detalhados, senhas seguras, emails únicos por timestamp
