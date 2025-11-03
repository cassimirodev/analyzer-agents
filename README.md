# Analyzer Agents 

Uma crew de agentes IA que coletam e analisam dados financeiros de forma autônoma, gerando um relatório sobre determinado tópico, utilizando o CrewAI.

# Como utilizar o projeto? 

### 1. Clonar o Repositório

Primeiro, clone o repositório para a sua máquina local:

```bash
git clone git@github.com:cassimirodev/analyzer-agents.git
cd analyzer_agents
```

### 2. Configurar o Ambiente Virtual

Com `python`:
```bash
python -m venv .venv
```

Com `uv`:
```bash
uv venv
```
Após a criação, ative o ambiente:

```bash
# Ativar o ambiente (Linux/macOS)
source .venv/bin/activate

# Ativar o ambiente (Windows)
.venv\Scripts\activate
```


### 3. Instalar as Dependências

Você pode usar `pip` ou `uv` para instalar as dependências listadas no arquivo `pyproject.toml`.

Com `pip`:
```bash
pip install .
```

Ou com `uv`:
```bash
uv pip install .
```


## Configuração das Chaves de API

Para que os agentes funcionem, você precisa fornecer chaves de API para os serviços de LLM e busca.

- Gere a chave do Gemini no [Google AI Studio ](https://aistudio.google.com/app/u/1/)
- Gere a chave do Serper no [Serper](https://serper.dev/)
- Crie um arquivo chamado `.env` na raiz do projeto.
- Seu .env parecerá com isso: 

```env
# Modelo de LLM utilizado
MODEL="Modelo Utilizado"

# Chave de API do Gemini
GEMINI_API_KEY="SUA_CHAVE_API_GEMINI"

# Chave de API do Serper
SERPER_API_KEY="SUA_CHAVE_API_SERPER"
```

Caso não queria utilizar o gemini, você pode mudar o provider [aqui](https://docs.crewai.com/en/concepts/llms).


## Rodando os Testes

O Código possui testes automatizados para verificar o funcionamento do código, rode com: 

```bash
pytest
```

## Rodando a API

O projeto inclui uma API FastAPI para interagir com os agentes.

### 1. Iniciar o Servidor


Para rodar a API em modo de desenvolvimento, execute o seguinte comando na raiz do projeto:

```bash
fastapi dev src/analyzer_agents/api/main.py
```


### 2. Usando os Endpoints

A API fornece a documentação interativa do Swagger UI em `localhost/docs`.

Para enviar um tópico para análise, você pode usar o endpoint `/analyze` com uma requisição POST.

Exemplo com Postman:

```bash
POST http://localhost:8000/analyze

{
  "topic": "NVIDIA"
}
```

O resultado da análise da crew será retornado na resposta.