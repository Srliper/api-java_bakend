# 🎨 CONFIGURANDO VS CODE PARA SPRING BOOT

## ✅ SIM, PODE USAR VS CODE!

O VS Code funciona **perfeitamente** para projetos Spring Boot Java. Na verdade, muitas pessoas preferem VS Code ao Eclipse!

---

## 📦 EXTENSÕES RECOMENDADAS

Instale estas extensões no VS Code para ter a melhor experiência:

### 1. Extension Pack for Java (Microsoft)
- **Nome:** `vscjava.vscode-java-pack`
- **O que faz:** Pacote completo com todas as ferramentas Java
- **Inclui:**
  - Language Support for Java
  - Debugger for Java
  - Test Runner for Java
  - Maven for Java
  - Project Manager for Java

### 2. Spring Boot Extension Pack (VMware)
- **Nome:** `vmware.vscode-spring-boot`
- **O que faz:** Suporte completo para Spring Boot
- **Inclui:**
  - Spring Boot Tools
  - Spring Initializr
  - Spring Boot Dashboard

### 3. Spring Boot Dashboard (VMware)
- **Nome:** `vscode-spring-boot-dashboard`
- **O que faz:** Painel visual para gerenciar aplicações Spring Boot

### Como Instalar:
1. Abra o VS Code
2. Clique no ícone de Extensions (ou `Ctrl+Shift+X`)
3. Procure pelo nome da extensão
4. Clique em "Install"

---

## 🚀 COMO ABRIR O PROJETO NO VS CODE

### Método 1: Abrir Pasta
1. Abra o VS Code
2. File → Open Folder (ou `Ctrl+K Ctrl+O`)
3. Selecione a pasta: `C:\Users\acer\Desktop\bakend-API\backend-api`
4. Pronto! O VS Code vai detectar o projeto Maven automaticamente

### Método 2: Via Terminal
```bash
cd C:\Users\acer\Desktop\bakend-API\backend-api
code .
```

---

## ✅ VERIFICAÇÕES AUTOMÁTICAS

O VS Code vai automaticamente:
- ✅ Detectar que é um projeto Maven
- ✅ Baixar dependências automaticamente
- ✅ Mostrar erros de compilação
- ✅ Oferecer autocomplete para Java
- ✅ Sugerir imports

---

## 🎯 FUNCIONALIDADES ÚTEIS NO VS CODE

### 1. Executar a Aplicação
- Abra o arquivo `BackendApiApplication.java`
- Clique no botão "Run" acima do método `main`
- Ou use `F5` para debug
- Ou use o terminal: `mvnw.cmd spring-boot:run`

### 2. Terminal Integrado
- `Ctrl + '` (aspas simples) abre o terminal
- Já fica na pasta do projeto
- Pode executar comandos Maven diretamente

### 3. Debug
- Coloque breakpoints clicando na margem esquerda
- Pressione `F5` para iniciar debug
- Use `F10` (step over) e `F11` (step into)

### 4. Gerenciar Dependências
- Abra `pom.xml`
- VS Code mostra as dependências
- Pode adicionar novas dependências facilmente

---

## 🔧 CONFIGURAÇÕES ÚTEIS

### settings.json (opcional)
Crie `.vscode/settings.json` na raiz do projeto:

```json
{
  "java.configuration.updateBuildConfiguration": "automatic",
  "java.compile.nullAnalysis.mode": "automatic",
  "spring-boot.ls.java.home": "",
  "java.configuration.runtimes": []
}
```

---

## 📝 ATALHOS ÚTEIS

| Ação | Atalho |
|------|--------|
| Abrir terminal | `Ctrl + '` |
| Executar | `Ctrl+F5` |
| Debug | `F5` |
| Formatar código | `Shift+Alt+F` |
| Buscar arquivo | `Ctrl+P` |
| Buscar em todos arquivos | `Ctrl+Shift+F` |
| Abrir comandos | `Ctrl+Shift+P` |

---

## 🎨 VANTAGENS DO VS CODE

✅ **Mais leve** que Eclipse  
✅ **Interface moderna** e intuitiva  
✅ **Extensões poderosas** para Java/Spring Boot  
✅ **Terminal integrado**  
✅ **Git integrado**  
✅ **Suporte a múltiplas linguagens**  
✅ **Gratuito e open source**  

---

## ⚠️ IMPORTANTE

### O que importa para o trabalho:
- ✅ **Código funcionando** (VS Code ou Eclipse, tanto faz!)
- ✅ **API testada no Postman**
- ✅ **Prints dos testes**
- ✅ **Link do GitHub funcionando**

**A professora não vai ver qual IDE você usou!** O importante é o código funcionar e os testes passarem.

---

## 🚀 TESTANDO NO VS CODE

1. **Abra o projeto no VS Code**
2. **Aguarde o VS Code baixar as dependências** (aparece no canto inferior direito)
3. **Execute no terminal:**
   ```bash
   mvnw.cmd spring-boot:run
   ```
4. **Teste no Postman** (igual ao guia anterior)

---

## 💡 DICA

Se o VS Code não detectar o projeto Java automaticamente:
1. Pressione `Ctrl+Shift+P`
2. Digite: "Java: Clean Java Language Server Workspace"
3. Selecione e aguarde reiniciar

---

## ✅ CONCLUSÃO

**SIM, pode usar VS Code tranquilamente!** 

Na verdade, muitos desenvolvedores preferem VS Code ao Eclipse hoje em dia. O importante é:
- ✅ Código funcionando
- ✅ Testes passando
- ✅ Prints corretos
- ✅ Link do GitHub funcionando

**Boa sorte com o trabalho! 🚀**

