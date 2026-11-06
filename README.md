# Automação de testes com Python, Behave e Selenium

Teste automatizado em BDD: um cenário escrito em Gherkin (português) abre o Firefox, pesquisa "Instituto Joga Junto" no Google e verifica se o site do Instituto foi aberto.

Projeto feito na Aula 9 da formação em QA e automação de testes (2025).

## Cenário

```gherkin
# language: pt
Funcionalidade: Acessar o site do Instituto Joga Junto pelo Google

  Cenário: Usuário realiza a busca e acessa o site com sucesso
    Dado que o navegador Firefox está aberto
    Quando eu pesquisar por "Instituto Joga Junto" no Google
    Então devo ver o site do Instituto aberto com sucesso
```

O passo **Então** falha se a URL aberta não for a do Instituto, para que o teste não aprove uma navegação errada.

## Tecnologias

- Python
- Behave (BDD com Gherkin)
- Selenium WebDriver com Firefox
- webdriver-manager (instala o GeckoDriver automaticamente)

## Estrutura

```
features/
├── buscar_site.feature        # cenário em Gherkin
└── steps/
    └── steps_buscar_site.py   # implementação de cada passo
requirements.txt
```

## Como executar

Pré-requisito: Firefox instalado.

```bash
python -m venv venv
venv\Scripts\activate          # Windows  (Linux/Mac: source venv/bin/activate)
pip install -r requirements.txt
behave
```

Observação: o Google pode exibir uma verificação anti-robô em buscas automatizadas; nesse caso, o teste falha no passo de busca.

## Créditos

Aula conduzida por Dione Braga e Diony Costa.
