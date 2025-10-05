# 🔍 Testes Exploratórios - API ServeRest

## 📋 Descrição

Esta coleção contém testes exploratórios para a API ServeRest, focando na descoberta de funcionalidades, validações de endpoints e identificação de comportamentos não documentados.

## 🎯 Objetivos dos Testes

- **Exploração de Endpoints:** Validar todos os endpoints disponíveis
- **Descoberta de Comportamentos:** Identificar respostas não documentadas
- **Validação de Dados:** Verificar estruturas de resposta
- **Cenários de Erro:** Testar comportamentos em situações adversas

## 📊 Cobertura de Testes

### 👤 Usuários (/usuarios)
- ✅ Listagem de usuários
- ✅ Cadastro de usuário
- ✅ Exclusão de usuário (cleanup)
- 🔄 Busca por ID (planejado)
- 🔄 Atualização de dados (planejado)
- 🔄 Validações de campo obrigatório (planejado)
- 🔄 Teste de duplicação de email (planejado)

### 🔐 Login (/login)
- ✅ Login com usuário válido
- 🔄 Login com credenciais inválidas (planejado)
- 🔄 Validação de token de autorização (planejado)
- 🔄 Teste de expiração de token (planejado)

### 🛍️ Produtos (/produtos)
- ✅ Listagem de produtos
- ✅ Cadastro de produto (autenticado)
- 🔄 Busca por ID (planejado)
- 🔄 Atualização de produto (planejado)
- 🔄 Exclusão de produto (planejado)
- 🔄 Upload de imagem (planejado)
- 🔄 Validações de estoque (planejado)

### 🛒 Carrinhos (/carrinhos)
- ✅ Listagem de carrinhos
- 🔄 Busca por ID (planejado)
- 🔄 Criação de carrinho (planejado)
- 🔄 Finalização de compra (planejado)
- 🔄 Cancelamento de compra (planejado)

## 🔧 Configuração

### Variáveis de Environment
```json
{
  "baseUrl": "https://serverest.dev",
  "userEmail": "",
  "userPassword": "",
  "authToken": "",
  "userId": "",
  "productId": "",
  "cartId": ""
}
```

### Pre-request Scripts
- Geração de dados aleatórios para testes
- Configuração automática de tokens
- Limpeza de dados entre testes

### Tests Scripts
- Validação de códigos de status
- Verificação de schemas JSON
- Testes de performance (tempo de resposta)
- Validação de headers de segurança

## 📈 Métricas Esperadas

- **Taxa de Sucesso dos Códigos de Status:** > 95%
- **Tempo de Resposta:** < 2000ms
- **Validação de Schema:** 100%
- **Cobertura:** Todos os endpoints principais

## 🐛 Bugs Identificados

*Documentar aqui quaisquer bugs ou comportamentos inesperados encontrados durante os testes exploratórios*

## 📝 Observações

- Todos os dados são criados e limpos automaticamente
- Não deixa dados residuais no servidor
- Testes podem ser executados repetidamente
- Coleção independente, não requer configuração externa

## 🔄 Próximos Passos

1. Expandir testes de segurança
2. Adicionar testes de valores limite
3. Implementar testes de carga básicos
4. Adicionar validações de acessibilidade da API

---

**Criado por:** Gabriel  
**Data:** Outubro 2025  
**LinkedIn:** [Post sobre testes exploratórios](#)
