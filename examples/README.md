# 📸 Exemplos de Resultados de Testes

Esta pasta contém screenshots e exemplos de execução das collections de teste.

## 📁 Estrutura de Organização

```
examples/
├── test-results-screenshots/
│   ├── exploratory-tests/
│   │   ├── collection-runner-success.png
│   │   ├── individual-request-example.png
│   │   ├── test-failures-example.png
│   │   └── newman-html-report.png
│   ├── functional-tests/
│   │   └── (futuras screenshots)
│   └── performance-tests/
│       └── (futuras screenshots)
├── sample-data/
│   ├── test-users.json
│   ├── test-products.json
│   └── test-scenarios.json
└── reports/
    ├── html-reports/
    └── json-reports/
```

## 🖼️ Screenshots de Exemplo

### Execução Bem-Sucedida
- **collection-runner-success.png:** Exemplo de execução completa sem falhas
- **individual-request-example.png:** Exemplo de request individual com validações

### Cenários de Falha
- **test-failures-example.png:** Como interpretar falhas de teste
- **debugging-process.png:** Processo de debug de problemas

### Relatórios
- **newman-html-report.png:** Exemplo de relatório HTML gerado pelo Newman
- **postman-monitor-results.png:** Resultados de monitoramento automático

## 📊 Dados de Exemplo

### Usuários de Teste
```json
{
  "validUser": {
    "nome": "Usuario Teste",
    "email": "teste@example.com",
    "password": "senha123",
    "administrador": "true"
  },
  "invalidUser": {
    "nome": "",
    "email": "email-invalido",
    "password": "123",
    "administrador": "maybe"
  }
}
```

### Produtos de Teste
```json
{
  "validProduct": {
    "nome": "Produto Teste",
    "preco": 100,
    "descricao": "Descrição do produto teste",
    "quantidade": 50
  },
  "invalidProduct": {
    "nome": "",
    "preco": -10,
    "descricao": "",
    "quantidade": "texto"
  }
}
```

## 📈 Métricas de Exemplo

### Tempo de Resposta Esperado
- **GET /usuarios:** < 200ms
- **POST /usuarios:** < 500ms
- **PUT /usuarios:** < 400ms
- **DELETE /usuarios:** < 300ms

### Taxa de Sucesso Esperada
- **Testes Exploratórios:** > 95%
- **Testes Funcionais:** > 98%
- **Testes de Regressão:** 100%

## 🎯 Como Adicionar Seus Resultados

1. Execute as collections
2. Capture screenshots dos resultados
3. Exporte relatórios HTML/JSON
4. Organize seguindo a estrutura de pastas
5. Documente anomalias ou bugs encontrados

## 📝 Legenda de Status

- 🟢 **Passou:** Teste executado com sucesso
- 🟡 **Aviso:** Teste passou mas com alertas
- 🔴 **Falhou:** Teste falhou, requer investigação
- ⚪ **Pulado:** Teste não executado (condições não atendidas)

---

**💡 Dica:** Use esta pasta como referência para entender os resultados esperados das suas execuções!
