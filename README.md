# 🧪 API Testing Collections - ServeRest

> **Collections de testes automatizados para a API ServeRest usando Postman**
> 
> 📝 *Conteúdo técnico compartilhado no LinkedIn sobre testes de API*

## 🎯 Sobre o Projeto

Este repositório contém collections de testes desenvolvidas para a API **[ServeRest](https://serverest.dev)** - uma API REST gratuita que simula uma loja virtual, ideal para praticar testes de API.

### 🔗 API Utilizada
- **Base URL:** `https://serverest.dev`
- **Documentação:** [ServeRest Docs](https://serverest.dev)
- **Swagger:** [API Documentation](https://serverest.dev/swagger)

## 📁 Estrutura do Repositório

```
📦 apiTesting/
├── 🧪 collections/
│   ├── 🔍 exploratory-tests/
│   │   ├── Testes_Exploratorios.postman_collection.json
│   │   └── README.md
│   ├── 🔧 functional-tests/
│   │   └── (futuras collections)
│   ├── 🚀 performance-tests/
│   │   └── (futuras collections)
│   └── 🔐 security-tests/
│       └── (futuras collections)
├── 📊 environments/
│   ├── ServeRest-DEV.postman_environment.json
│   └── ServeRest-PROD.postman_environment.json
├── 📋 documentation/
│   ├── test-strategy.md
│   └── postman-usage.md
└── 🎬 examples/
    └── test-results-screenshots/
```

## 🚀 Como Usar

### 📥 Download e Importação

1. **Clone ou faça fork do repositório:**
   ```bash
   git clone https://github.com/SEU-USUARIO/apiTesting.git
   ```

2. **Importe no Postman:**
   - Abra o Postman
   - Clique em `Import`
   - Selecione os arquivos `.json` das collections
   - Importe também os environments

3. **Configure o Environment:**
   - Selecione o environment `ServeRest-DEV`
   - Verifique se a `baseUrl` está configurada como `https://serverest.dev`

### 🎮 Executando os Testes

#### Testes Exploratórios
```bash
# Via Postman UI
1. Selecione a collection "Testes Exploratórios"
2. Clique em "Run Collection"
3. Configure as iterações e delay
4. Execute e analise os resultados

# Via Newman (CLI)
newman run collections/exploratory-tests/Testes_Exploratorios.postman_collection.json \
  -e environments/ServeRest-DEV.postman_environment.json \
  --reporters html,cli
```

## 📝 Collections Disponíveis

### 🔍 Testes Exploratórios
- **Arquivo:** `collections/exploratory-tests/Testes_Exploratorios.postman_collection.json`
- **Objetivo:** Exploração da API ServeRest
- **Cobertura:** Endpoints principais, validações básicas, cenários de erro
- **LinkedIn Post:** [Link do post](#)

### 🔄 Futuras Collections
- **Testes Funcionais:** Validações completas de funcionalidades
- **Testes de Performance:** Carga e stress testing
- **Testes de Segurança:** Validações de autenticação e autorização

## 🛡️ Política de Contribuição

### ⚠️ Importante
- **Apenas FORKS e DOWNLOADS são permitidos**
- **NÃO são aceitos Pull Requests**
- **NÃO são aceitas alterações diretas**

### 📋 Como Contribuir
1. Faça um **fork** do repositório
2. Trabalhe em seu próprio fork
3. Compartilhe seu trabalho independentemente
4. Para sugestões, abra uma **Issue** (apenas sugestões, não PRs)

## 🎯 Conteúdo LinkedIn

Este repositório serve como base para conteúdo técnico compartilhado no LinkedIn sobre:

- ✅ **Estratégias de Teste de API**
- ✅ **Automação com Postman**
- ✅ **Boas Práticas de Testing**
- ✅ **Collections Organizadas**
- ✅ **Cenários de Teste Realistas**

## 🔧 Requisitos

### Software Necessário
- **Postman** (versão 10.0+)
- **Newman** (opcional, para execução via CLI)
- **Node.js** (se usar Newman)

### Instalação Newman
```bash
npm install -g newman
npm install -g newman-reporter-html
```

## 📊 Métricas de Teste

Cada collection inclui:
- ✅ **Testes de Status Code**
- ✅ **Validação de Schema**
- ✅ **Testes de Response Time**
- ✅ **Validação de Headers**
- ✅ **Cenários Negativos**

## 🤝 Contato

- **LinkedIn:** [Seu perfil LinkedIn]
- **GitHub:** [Seu perfil GitHub]
- **Email:** [Seu email profissional]

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

⭐ **Se este conteúdo foi útil, considere dar uma estrela no repositório!**

📢 **Acompanhe no LinkedIn para mais conteúdo sobre testes de API!**
