# 🧪 Coleções de Testes de API - ServeRest

> **Coleções de testes automatizados para a API ServeRest usando Postman**
> 
> 📝 *Conteúdo técnico compartilhado no LinkedIn sobre testes de API*

## 🎯 Sobre o Projeto

Este repositório contém coleções de testes desenvolvidas para a API **[ServeRest](https://serverest.dev)** - uma API REST gratuita que simula uma loja virtual, ideal para praticar testes de API.

> 🚧 **Projeto em Construção:** Este repositório está sendo constantemente aprimorado para se tornar uma referência completa em testes de API. Novas coleções e funcionalidades serão adicionadas regularmente.

### 🔗 API Utilizada - ServeRest
- **URL Base:** `https://serverest.dev`
- **Documentação:** [Documentação ServeRest](https://serverest.dev)
- **Swagger:** [Documentação da API](https://serverest.dev/swagger)

### 🙏 Agradecimentos
**Agradecimento especial ao [Paulo Gonçalves](https://github.com/PauloGoncalvesBH)** e toda a comunidade **ServeRest** por disponibilizar esta excelente API gratuita para a comunidade de testes. A **ServeRest** é fundamental para o aprendizado e prática de testes de API no Brasil.

- **Repositório ServeRest:** https://github.com/ServeRest/ServeRest
- **Criador:** Paulo Gonçalves (@PauloGoncalvesBH)

## 📁 Estrutura do Repositório

```
📦 apiTesting/
├── 🧪 collections/
│   ├── 🔍 exploratory-tests/
│   │   ├── testesExploratorios.json
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

### 📦 Configuração do Servidor Local

**IMPORTANTE:** Para executar os testes, você precisa iniciar o servidor ServeRest localmente:

```bash
npx serverest@latest
```

O servidor será iniciado em `http://localhost:3000`

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
   - Selecione o environment `ServeRest-DEV (Local)`
   - Verifique se a `baseUrl` está configurada como `http://localhost:3000`
   - Certifique-se de que o servidor ServeRest está rodando

### 🎮 Executando os Testes

#### Testes Exploratórios
```bash
# 1. PRIMEIRO: Inicie o servidor local
npx serverest@latest

# 2. Via Interface do Postman
1. Selecione a coleção "1 - Testes Exploratorios"
2. Clique em "Run Collection"
3. Configure as iterações e delay
4. Execute e analise os resultados

# 3. Via Newman (CLI)
newman run collections/exploratory-tests/testesExploratorios.json \
  -e environments/ServeRest-DEV.postman_environment.json \
  --reporters html,cli
```

## 📝 Coleções Disponíveis

### 🔍 Testes Exploratórios
- **Arquivo:** `collections/exploratory-tests/testesExploratorios.json`
- **Objetivo:** CRUD completo de usuários com dados dinâmicos
- **Cobertura:** Endpoints /usuarios (CREATE, READ, UPDATE, DELETE)
- **Funcionalidades:**
  - Geração automática de dados únicos (gandalf_XXXX, mago_cor@hobbit.org)
  - Validações completas de status codes e mensagens
  - Fluxo end-to-end de usuários
- **Servidor:** Requer servidor local (`npx serverest@latest`)

### 🔄 Futuras Coleções
- **Testes Funcionais:** Validações completas de funcionalidades
- **Testes de Performance:** Testes de carga e stress
- **Testes de Segurança:** Validações de autenticação e autorização

## 🛡️ Política de Contribuição

### ⚠️ Importante - Repositório Fork-Only
- **✅ PERMITIDO:**
  - **Fazer FORK** do repositório
  - **Download** das coleções
  - **Issues** para sugestões e dúvidas
  - **Stars** no repositório

- **❌ NÃO PERMITIDO:**
  - **Pull Requests** (não serão aceitos)
  - **Commits diretos** na branch main
  - **Merge** de código externo
  - **Alterações nas branches** principais
  - **Modificações colaborativas**

### 📋 Como Contribuir
1. **Faça um FORK** do repositório para sua conta
2. **Trabalhe livremente** em seu próprio fork
3. **Use como base** para seus projetos pessoais
4. **Para sugestões:** Abra uma **Issue** (apenas sugestões, não código)
5. **Compartilhe** seu trabalho derivado independentemente

> **💡 Filosofia:** Este é um repositório pessoal de portfólio. Forks são encorajados para uso e aprendizado, mas o código principal é mantido pelo autor original.

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

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

⭐ **Se este conteúdo foi útil, considere dar uma estrela no repositório!**

📢 **Acompanhe no LinkedIn para mais conteúdo sobre testes de API!**
