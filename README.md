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


```bash
# Criar o ambiente virtual
python -m venv .venv

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

Caso não queria utilizar o gemini, você pode mudar o provider [aqui](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project).


## Rodando os Testes

Como o projeto ainda não está finalizado, utilize os testes automatizados para testar o código:

```bash
pytest
```
