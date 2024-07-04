# Fastapi

- Acessar a aplicação na rede Petrobras: `http://10.27.36.13:8000/`

- Iniciar servidor de desenvolvimento (com a CLI do `fastapi`): `fastapi dev fast_zero/app.py --host 0.0.0.0 --port 8000 --reload`

- Iniciar servidor de desenvolvimento (diretamente com `uvicorn`): `uvicorn fast_zero.app:app --host 0.0.0.0 --port 8000 --reload`

- Quando queremos expor um erro al cliente, devemos levantar(raise) uma **_Exception_** de HTTP

```python
from fastapi import HTTPException
...
raise HTTPException(status_code=HTTPStatus.NOT_FOUND, detail="usuário não encontrado")
```

- É uma boa prática no desenvolvimento de aplicaçoes separar as configurações do código. Configurações, como credenciais de banco de dados, são propensas a mudanças entre diferentes ambientes (DSV, HMG e PRD). Misturá-las com o código pode tornar o processo de mudança entre ambientes complicado e propenso a erros. **12 fatores para a construção de uma aplicação**. Para ajudar nisso:
  ` poetry add pydantic-settings`
