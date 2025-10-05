# 🚀 Configuração Inicial do Projeto

Este documento guia você através da configuração inicial do projeto Coleções de Teste de API.

## 📋 Pré-requisitos

### Software Necessário
- **Git** (versão 2.20+)
- **Postman** (versão 10.0+)
- **Node.js** (versão 16+) - opcional, para Newman
- **NPM** (incluído com Node.js) - opcional, para Newman

### Verificar Instalações
```bash
# Verificar Git
git --version

# Verificar Node.js (opcional)
node --version

# Verificar NPM (opcional)
npm --version
```

## 📥 Setup do Projeto

### 1. Clone/Download do Repositório

#### Opção A: Clone (recomendado)
```bash
git clone https://github.com/SEU-USUARIO/apiTesting.git
cd apiTesting
```

#### Opção B: Download ZIP
1. Clique em "Code" > "Download ZIP" no GitHub
2. Extraia o arquivo
3. Navegue até a pasta extraída

### 2. Verificar Estrutura
```bash
# Listar arquivos principais
ls -la

# Deve mostrar:
# - README.md
# - collections/
# - environments/
# - documentation/
# - examples/
```

## 📦 Importação no Postman

### 1. Abrir Postman
- Inicie o aplicativo Postman
- Faça login (recomendado para salvar collections)

### 2. Importar Environment
1. Clique em **Import** (canto superior esquerdo)
2. Selecione **Upload Files**
3. Navegue até: `environments/ServeRest-DEV.postman_environment.json`
4. Clique **Import**

### 3. Importar Collection
1. Clique em **Import** novamente
2. Selecione **Upload Files**
3. Navegue até: `collections/exploratory-tests/testesExploratorios.json`
4. Clique **Import**

### 4. Configurar Environment
1. No canto superior direito, clique no dropdown de environments
2. Selecione **ServeRest - DEV Environment**
3. Verifique se `baseUrl` está definida como `https://serverest.dev`

## 🧪 Primeira Execução

### Teste Individual
1. Expanda a collection **Testes Exploratórios**
2. Clique em **👤 Usuários** > **Listar usuários**
3. Clique **Send**
4. Verifique se retorna status 200

### Execução Completa
1. Clique com botão direito na collection
2. Selecione **Run collection**
3. Configure:
   - Iterations: 1
   - Delay: 1000ms
4. Clique **Run Testes Exploratórios**

## 🔧 Configuração Newman (Opcional)

### Instalação
```bash
# Instalar Newman globalmente
npm install -g newman

# Instalar reporter HTML
npm install -g newman-reporter-html
```

### Teste de Instalação
```bash
# Verificar Newman
newman --version

# Executar collection via CLI
newman run collections/exploratory-tests/testesExploratorios.json \
  -e environments/ServeRest-DEV.postman_environment.json
```

## 📊 Verificação de Funcionamento

### Checklist de Verificação
- [ ] **Environment importado** corretamente
- [ ] **Collection importada** e visível
- [ ] **Teste individual** executa com sucesso
- [ ] **Collection completa** executa sem erros
- [ ] **Newman** (opcional) funciona via CLI

### Resultados Esperados
- **Status codes:** Principalmente 200, 201
- **Response times:** < 2000ms
- **Test results:** Todos passando (verde)
- **No errors:** Sem falhas de conexão

## 🐛 Resolução de Problemas

### Problema: Environment não selecionado
**Sintoma:** Variáveis aparcem como `{{baseUrl}}`
**Solução:** Selecionar environment no dropdown superior direito

### Problema: API não responde
**Sintoma:** Timeout ou erro de conexão
**Solução:** 
1. Verificar https://serverest.dev no browser
2. Verificar conexão com internet
3. Tentar novamente após alguns minutos

### Problema: Collection não importa
**Sintoma:** Erro na importação
**Solução:**
1. Verificar se arquivo não está corrompido
2. Tentar reimportar
3. Verificar se Postman está atualizado

### Problema: Newman não encontrado
**Sintoma:** `command not found: newman`
**Solução:**
```bash
# Verificar se Node.js está instalado
node --version

# Reinstalar Newman
npm install -g newman
```

## 📞 Suporte

### Documentação Adicional
- [Guia de Uso do Postman](documentation/postman-usage.md)
- [Estratégia de Testes](documentation/test-strategy.md)
- [README da Collection](collections/exploratory-tests/README.md)

### Reportar Problemas
- **Issues:** Use templates no GitHub
- **LinkedIn:** Comente nos posts relacionados

## ✅ Próximos Passos

Após a configuração inicial:

1. **Explorar a collection** - Execute requests individuais
2. **Entender os testes** - Analise os scripts de validação
3. **Personalizar** - Adapte para suas necessidades
4. **Compartilhar** - Faça fork e crie suas versões
5. **Acompanhar** - Fique atento às atualizações

---

**🎉 Parabéns!** Você configurou com sucesso o projeto API Testing Collections!

**📈 Próximo nível:** Explore outras collections quando estiverem disponíveis!
