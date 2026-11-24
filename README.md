# API de Chamados de Suporte

> Projeto desenvolvido na Disciplina de Programação para Web — Curso de Análise e Desenvolvimento de Sistemas da Universidade Federal do Cariri (UFCA).

**Instituição:** Universidade Federal do Cariri (UFCA)  
**Curso:** Análise e Desenvolvimento de Sistemas  
**Disciplina:** Programação para Web  
**Professor:** Jair Alencar  
**Tutora:** Mônica Paz  
**Estudante:** Antonio Alex Dayson Tomaz  
**Entrega:** Semana 01 (`tag: semana-01`)  


---

## 1. Objetivo do Projeto

Desenvolver uma API REST para auxiliar uma equipe de Tecnologia da Informação (TI) a registrar solicitações e acompanhar o atendimento de chamados de suporte.

Nesta **primeira etapa (Semana 01)**, o objetivo é estruturar a base inicial da aplicação em Python utilizando o framework **Flask** e o gerenciador de pacotes **uv**, reproduzindo o desenvolvimento apresentado na videoaula *"Criando a primeira API com Flask"*. Esta versão inicial implementa a comunicação básica cliente-servidor via HTTP/JSON por meio da rota raiz (`GET /`), sem persistência em banco de dados ou cadastro de chamados neste momento.

---

## 2. Estrutura do Repositório

```text
├── src/
│   └── chamados_ads/
│       └── __init__.py # Módulo inicial gerado automaticamente pelo uv
├── .gitignore          # Ficheiros e diretórios ignorados pelo Git (.venv/, __pycache__/, etc.)
├── .python-version     # Versão do Python utilizada no projeto
├── LICENSE             # Licença do repositório
├── README.md           # Documentação institucional e instruções de execução
├── app.py              # Código-fonte da aplicação Flask e definição da rota inicial
├── pyproject.toml      # Metadados do projeto e declaração de dependências
└── uv.lock             # Ficheiro de bloqueio com as versões exatas das dependências
```

---

## 3. Instalação das Dependências

Certifique-se de ter o **Python** e o gerenciador **[uv](https://docs.astral.sh/uv/)** instalados no ambiente.

1. Clone o repositório e acesse a pasta do projeto:
   ```bash
   git clone https://github.com/alexdaysonufca/chamados-ads.git
   cd chamados-ads
   ```

2. Instale as dependências exatamente conforme registradas no arquivo `uv.lock`:
   ```bash
   uv sync --locked
   ```

---

## 4. Como Executar a Aplicação

### Execução no GitHub Codespaces (ou com acesso externo)
Para iniciar o servidor Flask escutando em todas as interfaces de rede na porta `5000`:
```bash
uv run flask --app app run --host=0.0.0.0 --port=5000
```

### Execução em Ambiente Local
Caso esteja executando diretamente em sua máquina local:
```bash
uv run flask --app app run --port=5000
```

Após iniciar, a aplicação ficará disponível em `http://localhost:5000`.

---

## 5. Como Acessar a Rota Inicial e Resposta Esperada

Com a aplicação em execução, realize uma requisição **GET** para a rota raiz (`/`):

* **Pelo navegador:** acesse `http://localhost:5000/` (ou a URL pública encaminhada pela porta `5000` no Codespaces).
* **Pelo terminal (usando `curl`):**
  ```bash
  curl -i http://localhost:5000/
  ```

### Resposta Esperada
* **Código de Status HTTP:** `200 OK`
* **Cabeçalho:** `Content-Type: application/json`
* **Corpo da Resposta (JSON):**
  ```json
  {
    "mensagem": "API de chamados em funcionamento"
  }
  ```
