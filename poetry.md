# Poetry

- Instalar poetry globalmente: `pip install poetry`
- Criar um projeto: `poetry new fast_zero`
- Alterar `python "^3.11"` para `python "3.11.*"` no arquivo `pyproject.toml`, em `[tool.poetry.dependencies]`
- Dentro do diretório do projeto, fazer `poetry install` para criar o ambiente virtual. No Windows, o ambiente virtual é criado em `C:\Users\U4EA\AppData\Local\pypoetry\Cache\virtualenvs`
- Adicionar `fastapi` ao ambiente virtual: `poetry add fastapi`
- Habilitar o ambiente virtual: `poetry shell`

- Instalando dependências de desenvolvimente: `poetry add --group dev pytest pytest-cov taskipy ruff httpx`

- Após a instalação das ferramentas de desenvolvimento, precisamos configurá-las individualmente no arquivo `pyproject.toml`
