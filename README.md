# 🧪 Coleções de Testes de API - ServeRest

> **Coleções de testes automatizados para a API ServeRest usando Postman**
> 
> *Conteúdo técnico compartilhado no LinkedIn sobre testes de API*

## 🎯 Sobre o Projeto

Este repositório contém coleções de testes desenvolvidas para a API **[ServeRest](https://serverest.dev)** - uma API REST gratuita que simula uma loja virtual, ideal para praticar testes de API.

> 🚧 **Projeto em Construção:** Este repositório está sendo constantemente aprimorado para se tornar uma referência completa em testes de API. Novas coleções e funcionalidades serão adicionadas regularmente.

### API Utilizada - ServeRest
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
│   └── 🔍 exploratory-tests/
│       ├── testesExploratorios.json ✅ (CRUD completo validado)
│       └── README.md
├── 📊 environments/
│   └── ServeRest-DEV.postman_environment.json ✅ (localhost:3000)
├── 📋 documentation/
│   ├── test-strategy.md
│   └── postman-usage.md
├── 🔧 .github/workflows/
│   └── collection-validation.yml ✅ (CI/CD configurado)
└── 📝 documentação/
    ├── README.md (principal)
    ├── CONTRIBUTING.md (política fork-only)
    ├── PROJETO_PRONTO.md (status final)
    ├── SETUP.md (guia configuração)
    └── TESTES_VALIDADOS.md (relatório 100% sucesso)
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

### 🔍 Testes Exploratórios ✅ 100% Validados
- **Arquivo:** `collections/exploratory-tests/testesExploratorios.json`
- **Status:** ✅ **TODOS OS TESTES PASSANDO** (7/7 assertions)
- **Cobertura:** CRUD completo de usuários
  - ✅ POST /usuarios (criar usuário)
  - ✅ GET /usuarios/{id} (buscar por ID)
  - ✅ PUT /usuarios/{id} (atualizar dados)
  - ✅ GET /usuarios (listar todos)
  - ✅ DELETE /usuarios/{id} (deletar)
- **Funcionalidades Especiais:**
  - Geração automática de dados únicos (gandalf_XXXX)
  - Emails criativos com paleta de cores (mago_cor@hobbit.org)
  - Fluxo end-to-end completo com cleanup
  - Performance: ~13ms tempo médio
- **Servidor:** ⚠️ **OBRIGATÓRIO** executar `npx serverest@latest`
- **Base URL:** `http://localhost:3000`

### 🔄 Próximas Funcionalidades (Planejadas)
- **Testes Funcionais:** Validações completas de todos os endpoints
- **Testes de Performance:** Testes de carga e stress
- **Testes de Segurança:** Validações de autenticação e autorização

## 📊 Resultados Validados

### ✅ Status Atual (100% Funcional)
```
Requests executados: 5/5 
Assertions validadas: 7/7   
Tempo médio: 13ms
Taxa de sucesso: 100%
CI/CD: Funcionando
```

### 🎲 Dados Dinâmicos Validados
- **Nomes únicos:** `gandalf_1728147123456`
- **Emails criativos:** `mago_azul@hobbit.org` (25+ cores)
- **Senhas dinâmicas:** `senha1728147123456`
- **Administrador:** `true` (fixo)

## 🛡️ Política de Contribuição

### ⚠️ Importante - Repositório Fork-Only
- **PERMITIDO:**
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
Para sugestões ou dúvidas, **entre em contato pelo LinkedIn:**

**📱 LinkedIn:** [Gabriel Roquim](https://www.linkedin.com/in/gabsqa/)

1. **Faça um FORK** do repositório para sua conta
2. **Trabalhe livremente** em seu próprio fork  
3. **Use como base** para seus projetos pessoais
4. **Para sugestões:** Envie mensagem no LinkedIn
5. **Compartilhe** seu trabalho derivado independentemente

> **💡 Filosofia:** Este é um repositório pessoal de portfólio. Forks são encorajados para uso e aprendizado, mas o código principal é mantido pelo autor original.

## 🎯 Conteúdo LinkedIn

Este repositório serve como base para conteúdo técnico compartilhado no LinkedIn sobre:

-  **Estratégias de Teste de API** (implementadas)
- **Automação com Postman** (CRUD completo validado)
- **Boas Práticas de Teste** (dados dinâmicos únicos)
- **Coleções Organizadas** (estrutura profissional)
- **Cenários de Teste Realistas** (100% funcionais)
- **CI/CD com GitHub Actions** (validação automática)

**📱 Acompanhe:** [Gabriel Roquim](https://www.linkedin.com/in/gabsqa/)

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

## 📊 Métricas de Teste Validadas

### ✅ Testes Implementados e Funcionando
- **Testes de Código de Status** (201, 200, 200, 200, 200)
- **Validação de Mensagens** ("Cadastro realizado com sucesso", etc.)
- **Testes de Campos Obrigatórios** (nome, email, administrador)
- **Validação de Dados Únicos** (timestamp-based)
- **Testes de Performance** (~13ms tempo médio)
- **Cenários End-to-End** (criar → buscar → atualizar → listar → deletar)

### 📈 Estatísticas Reais
- **Total de Requests:** 5
- **Total de Assertions:** 7
- **Taxa de Sucesso:** 100%
- **Tempo de Execução:** ~200ms total
- **Dados Transferidos:** ~3.75kB

## 🤝 Contato

- **📱 LinkedIn:** [Gabriel Roquim](https://www.linkedin.com/in/gabsqa/)
- **🔗 GitHub:** [gabrielroquim](https://github.com/gabrielroquim)

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

⭐ **Se este conteúdo foi útil, considere dar uma estrela no repositório!**

📢 **Acompanhe no LinkedIn para mais conteúdo sobre testes de API:** [Gabriel Roquim](https://www.linkedin.com/in/gabsqa/)
