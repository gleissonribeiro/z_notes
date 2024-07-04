# Alembic

- Iniciar o _alembic_: `alembic init <diretorio_com_migracoes>`

## Dentro da pasta de migrações

- Dentro do arquivo `env.py` é onde estão as configurações das migrações;
- Dentro do arquivo `.mako` é o _template_ de migrações;

## Arquivo _alembic.ini_ na raiz do projeto

- Onde estão as configurações do _alembic_ (URL para o banco, pasta de migrações, etc)

## Alterando o conteúdo de _settings.py_ dentro da pasta com as migrações

- Precisamos dizer ao _alembic_ onde está o banco de dados:

```python
    # migrations/env.py

    from fast_zero.settings import Settings
   ...
    config = context.config
    config.set_main_option('sqlalchemy.url', Settings().DATABASE_URL)
    ...

```

- Também precisamos informar onde estão os metadados:

```python
    # migrations/env.py

    from fast_zero.models import table_registry
    ...
    target_metadata = table_registry.metadata
    ...

```

## Gerando migrações

- `alembic revision --autogenerate -m "create users table"`

- Pode ser necessário ajustar os comandos gerados automaticamente pelo _alembic_ no arquivo
  com a migração

- O _alembic_ cria uma tabela no banco, chamada **_alembic_version_** para gerenciar as migrações

## Aplicanado as migrações no banco

- `alembic upgrade head`
