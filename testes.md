# Testes

### Estratégia AAA para criar testes: **Arrange**, **Act** e **Assert**

```python
from http import HTTPStatus

from fastapi.testclient import TestClient

from fast_zero.app import app


def test_root_deve_retornar_ok_e_ola_mundo():
    client = TestClient(app)  # Arrange

    response = client.get('/')  # Act

    assert response.status_code == HTTPStatus.OK  # Assert
    assert response.json() == {'message': 'Olá Mundo!'}  # Assert
```

### Algumas regras do _pytest_

1. Os nomes dos arquivos de teste precisam começar com **_test_** (ex.: **_test_app.py_**);
2. O arquivo **_conftest.py_** precisa ter extamente esse nome e ficar dentro da pasta **_tests_**

### Para não precisar criar um cliente em todos os testes

```python
import pytest
...

@pytest.fixture()
def client():
    return TestClient(app)


def teste_01(client):
    ...
def teste_02(client):
    ...
```

### Geralmente as fixtures ficam no arquivo _conftest.py_ dentro da pasta _tests_

```python
# /tests/conftest.py

import pytest
from fastapi.testclient import TestClient

from fast_zero.app import app


@pytest.fixture()
def client():
    return TestClient(app)
```
