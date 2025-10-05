# 🧪 Coleções de Testes de API - ServeRest

> **Coleções de testes automatizados para a API ServeRest usando Postman**
> 
> 📝 *Conteúdo técnico compartilhado no LinkedIn sobre testes de API*

## 🎯 Sobre o Projeto

Este repositório contém coleções de testes desenvolvidas para a API **[ServeRest](https://serverest.dev)** - uma API REST gratuita que simula uma loja virtual, ideal para praticar testes de API.

### 🔗 API Utilizada
- **URL Base:** `https://serverest.dev`
- **Documentação:** [Documentação ServeRest](https://serverest.dev)
- **Swagger:** [Documentação da API](https://serverest.dev/swagger)

## 📁 Estrutura do Repositório

```
📦 apiTesting/
├── 🧪 collections/
│   ├── 🔍 exploratory-tests/
│   │   ├── Testes_Exploratorios.postman_collection.json
│   │   └── README.md
│   ├── 🔧 functional-tests/
│   │   └── (futuras coleções)
│   ├── 🚀 performance-tests/
│   │   └── (futuras coleções)
│   └── 🔐 security-tests/
│       └── (futuras coleções)
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
   git clone https://github.com/gabrielroquim/apiTesting.git
   ```

2. **Importe no Postman:**
   - Abra o Postman
   - Clique em `Import`
   - Selecione os arquivos `.json` das coleções
   - Importe também os environments

3. **Configure o Environment:**
   - Selecione o environment `ServeRest-DEV`
   - Verifique se a `baseUrl` está configurada como `https://serverest.dev`

### 🎮 Executando os Testes

#### Testes Exploratórios
```bash
# Via Interface do Postman
1. Selecione a coleção "Testes Exploratórios"
2. Clique em "Run Collection"
3. Configure as iterações e delay
4. Execute e analise os resultados

# Via Newman (CLI)
newman run collections/exploratory-tests/Testes_Exploratorios.postman_collection.json \
  -e environments/ServeRest-DEV.postman_environment.json \
  --reporters html,cli
```

## 📝 Coleções Disponíveis

### 🔍 Testes Exploratórios
- **Arquivo:** `collections/exploratory-tests/Testes_Exploratorios.postman_collection.json`
- **Objetivo:** Exploração da API ServeRest
- **Cobertura:** Endpoints principais, validações básicas, cenários de erro
- **Post LinkedIn:** [Link do post](#)

### 🔄 Futuras Coleções
- **Testes Funcionais:** Validações completas de funcionalidades
- **Testes de Performance:** Testes de carga e stress
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
- ✅ **Boas Práticas de Teste**
- ✅ **Coleções Organizadas**
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

Cada coleção inclui:
- ✅ **Testes de Código de Status**
- ✅ **Validação de Schema**
- ✅ **Testes de Tempo de Resposta**
- ✅ **Validação de Headers**
- ✅ **Cenários Negativos**

## 🤝 Contato

- **LinkedIn:** [Gabriel Roquim](https://linkedin.com/in/gabrielroquim)
- **GitHub:** [gabrielroquim](https://github.com/gabrielroquim)
- **Email:** [Seu email profissional]

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

⭐ **Se este conteúdo foi útil, considere dar uma estrela no repositório!**

📢 **Acompanhe no LinkedIn para mais conteúdo sobre testes de API!**
