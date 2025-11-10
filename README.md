# 🤖 Aula 9 – Automação de Testes com Python, Behave e Selenium

### ✍️ Facilitadores  
**Dione Braga**  **e** **Diony Costa**

---

## 🎯 Objetivo da Aula

Aprender a **configurar o ambiente de automação de testes** com Python, utilizando **Behave** (BDD) e **Selenium WebDriver**, explorando o funcionamento do DOM, HTML, CSS e ferramentas de apoio como **Chocolatey** e **VSCode Extensions**.  
Ao final da aula, cada squad será capaz de criar e executar seu **primeiro script automatizado**.

---

## 🧱 Estrutura de Pastas

```
Aula 9 - Automacao/
│
├── features/
│   ├── buscar_site.feature
│   └── steps/
│       └── steps_buscar_site.py
│
├── test_automacao.py
└── requirements.txt
```

---

## ⚙️ Preparando o Ambiente

### 🪟 Passo 1 – Criar o projeto

Abra o **PowerShell** e execute:

```powershell
cd Desktop
mkdir "Aula_QA_2025"
cd "Aula_QA_2025"
mkdir "Aula 9 - Automacao"
cd "Aula 9 - Automacao"
```

---

### 🧩 Passo 2 – Criar ambiente virtual e ativar

```powershell
python -m venv venv
.venv\Scripts\Activate.ps1
```

💡 *O ambiente virtual (venv) isola as bibliotecas do projeto para evitar conflitos.*

---

### 📦 Passo 3 – Instalar dependências

```powershell
pip install behave selenium
pip freeze > requirements.txt
```

---

## ▶️ Executando o Projeto

Para rodar o teste:

```powershell
behave
```

📊 **Exemplo de saída esperada:**
```
1 feature passed, 0 failed, 0 skipped
1 scenario passed, 0 failed, 0 skipped
3 steps passed, 0 failed, 0 skipped
```

💬 Isso indica que sua automação foi executada com sucesso.

---

## 🌐 Uvicorn (para contextualização)

> **Uvicorn** é um servidor de aplicação ASGI (Asynchronous Server Gateway Interface) rápido e leve para Python, projetado para hospedar aplicações web e APIs. Ele executa seu código Python, recebendo requisições web e repassando-as para o aplicativo, como os frameworks FastAPI, Starlette e Django.

---

## 🧰 Extensões úteis do VSCode

Antes de prosseguir, explore essas extensões com o time:

| Extensão | Função |
|-----------|--------|
| 🧮 **Rainbow CSV** | Destaca colunas em arquivos `.csv` com cores, útil para analisar planilhas de testes. |
| 📓 **Jupyter Notebook** | Executa blocos de código Python interativos dentro do VSCode. |
| 💡 **Cursor** | VSCode com IA integrada — ajuda a escrever e entender código rapidamente. |

🕒 **Atividade:** explore cada extensão por 10 minutos e anote como ela pode ser útil em automação.

---

## 🧩 Entendendo o Selenium

O **Selenium** é uma biblioteca **open source** (código aberto) licenciada sob a Apache 2.0, compatível com quase todos os navegadores.  
É simples, poderoso e reconhecido oficialmente pelo **W3C (World Wide Web Consortium)**.

### 🔧 Componentes do Selenium

| Componente | Função |
|-------------|--------|
| **Selenium IDE** | Extensão de navegador que grava e reproduz ações. Ideal para iniciantes. |
| **Selenium Grid** | Executa testes em múltiplas máquinas e navegadores simultaneamente. |
| **Selenium WebDriver** | Controla o navegador via código Python. É o que usamos aqui. |

---

### 🧭 Configurando o Selenium IDE no navegador

1. Vá até a Chrome Web Store ou Edge Add-ons.  
2. Pesquise por **“Selenium IDE”**.  
3. Clique em **Adicionar ao navegador**.  
4. Crie um novo projeto e grave uma automação que abra o site do **Instituto Joga Junto**.  
5. Execute e observe o fluxo.

---

## 🎨 HTML e CSS

Pense que estamos construindo **uma casa na web**:

- 🧱 **HTML (HyperText Markup Language)** → é a estrutura (paredes, janelas, portas).  
- 🎨 **CSS (Cascading Style Sheets)** → é a pintura e decoração (cores, estilos, fontes).  

### Principais atributos HTML:

| Atributo | Função |
|-----------|--------|
| **id** | Identificador único de um elemento. |
| **class** | Agrupa elementos com características semelhantes. |
| **style** | Aplica estilos diretamente no elemento. |
| **title** | Mostra uma dica (tooltip) ao passar o mouse. |

---

## 🌳 DOM (Document Object Model)

O **DOM** representa a estrutura hierárquica do documento HTML como uma árvore de elementos.

💡 **Exemplo:**
```python
driver.find_element("id", "nome")
driver.find_element("xpath", "//button[text()='Enviar']")
```

> O Selenium interage com o **DOM**, encontrando elementos e executando ações como clicar, digitar e validar.

---

## 🍫 Chocolatey

### O que é?
O **Chocolatey** é um gerenciador de pacotes para Windows — semelhante ao `apt` (Ubuntu) e `yum` (Red Hat).  
Ele facilita a instalação de softwares essenciais para o QA.

---

### 📥 Instalação do Chocolatey

Execute no **PowerShell (como administrador):**

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

---

### 📦 Instale os pacotes necessários

```powershell
choco install selenium-all-drivers
choco install selenium
choco install firefox
```

✅ Isso garante compatibilidade entre Selenium e os navegadores.

---

## 🚀 Subindo o Projeto no GitHub

### 1️⃣ Inicialize o repositório

```powershell
git init
git add .
git commit -m "Primeira automação com Behave e Selenium"
```

### 2️⃣ Crie o repositório remoto

1. Vá até [github.com/new](https://github.com/new)
2. Nomeie o repositório (ex: `aula9_automacao`)
3. Copie o link HTTPS e conecte:

```powershell
git remote add origin https://github.com/SEU_USUARIO/aula9_automacao.git
git push -u origin main
```

---

## 🌿 Criar uma Branch

```powershell
git checkout -b ajustes-explicacao
git add .
git commit -m "Adiciona melhorias e explicações da aula"
git push origin ajustes-explicacao
```

> 💬 **Explicação:** as *branches* permitem testar sem alterar o código principal.

---

## 💻 Desafio do Caique 1 — Automação Individual

Crie um script que:
1. Abra o navegador.  
2. Pesquise “Instituto Joga Junto” no Google.  
3. Acesse o site e envie a mensagem:  
   `"Meu primeiro script de automação - NOME DA SUA SQUAD"`.

---

## 🤝 Desafio do Caique 2 — Automação em Squad

1. Automatize o acesso ao **WhatsApp Web**.  
2. Envie a mensagem:  
   `"Automação do WhatsApp - NOME DO SEU SQUAD"`.  
3. Suba o código em um repositório no GitHub da sua squad.

---

## 🧠 Conceitos que Devem Ser Reforçados

- O que é automação de testes? “Automação de testes é fazer o computador testar por nós, de forma rápida e repetitiva.”  
- Diferença entre testar manualmente e automatizar. "No teste manual, o QA precisa clicar, preencher formulários e observar os resultados. Na automação, o QA cria um roteiro de código e o computador repete o teste automaticamente, sempre igual, economizando tempo e reduzindo falhas humanas."
- Que o Selenium é uma biblioteca que **controla navegadores**.  
- Que o Behave permite escrever testes em **linguagem natural (BDD)**.  
- Importância do HTML, CSS e DOM para os seletores e testes automatizados.  
- Uso de ambientes virtuais e versionamento com Git/GitHub.

---

## 📜 Conclusão

Nesta aula você aprendeu a:

✅ Criar um ambiente virtual  
✅ Instalar e rodar o Behave com Selenium  
✅ Criar e versionar o projeto no GitHub  
✅ Entender HTML, CSS e DOM na automação  
✅ Utilizar Chocolatey para instalar pacotes  
✅ Trabalhar com **branches** e **squads**  

> “A automação é o próximo passo da qualidade. Ela não substitui o olhar humano, mas potencializa a eficiência do QA.”

---


