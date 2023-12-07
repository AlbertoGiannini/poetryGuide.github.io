# Guia de utilização do Poetry 
    

O Poetry é um gerenciador de dependências e pacotes do Python, facilitando o desenvolvimento dos programas. Utilizando Venvs, cada projeto é isolado das dependências e versões do sistema, evitando possíveis conflitos. [python-poetry.org](https://python-poetry.org/)
## Comandos básicos do Poetry
#### Instalando o  Poetry
```bash
pip install poetry
```
#### Criando um novo projeto
```bash
poetry new nome-da-pasta 
        
cd nome-da-pasta
```

#### Inicializando o Poetry em um projeto existente
```bash
cd pasta-do-projeto

poetry init 
```
#### Adicionando, removendo e instalando pacotes
- Adicionar pacote - `poetry add nome-do-pacote`

- Remover pacote - `poetry remove nome-do-pacote` 

- Atualizar as dependencias do pacote - `poetry update nome-do-pacote`

- Instalar os pacotes e as configurações - `poetry install`

- Instalar apenas dependências do projeto (Em projetos existentes) - `poetry install --no-root`

   
    
#### Executando o projeto no Poetry
Antes de executar um projeto com o Poerty, SEMPRE inicialize a Venv para não executar o programa utilizando as dependências do sistema.

- Inicializar a Venv - `poerty shell`

- Excecutar o arquivo - `python nome-do-arquivo.py`

ou

- Excecutar o arquivo `poetry run python nome-do arquivo.py`

#### Acessando as configurações do Poetry
É possível alterar as configurações do Poetry, para acessá-las use `poetry config --list` para listar as configurações do Poetry
## Gerenciando as Venvs
As venvs por padrão são ciradas no path do Poetry, isso pode ser alterado usando o comando 

```bash
poetry config virtualenvs.in-project true
``` 

O Poetry por padrão cria uma venv usando o path do python padrão instalado, o diterório das venvs ficam por padrão na pasta do poetry.

- Cria uma venv com o path - `poetry use env python` 

- Inicializa a venv / Cria uma com o path padrão do sistema - `poetry shell`

## Instalando e usando o Pyenv
É possível criar venvs com outras versões do Python e usá-las no Poetry, para facilitar a instalação
das versões, pode ser usado o pacote "pyenv-win" que gerencia as versões do Python. 
O pyenv originalmente suporta macOs e Unix, saiba mais em: [github.com/pyenv](https://github.com/pyenv/pyenv) 
#### Instalando o Pyenv no PowerShell

- Cria uma pasta no diretório do usuário e instala o Pyenv - `pip install pyenv-win --target \.pyenv`

#### Adicionando o pyenv no path
```bash
[System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User") 

[System.Environment]::SetEnvironmentVariable('PYENV_ROOT',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")

[System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
    
[System.Environment]::SetEnvironmentVariable('path', $env:USERPROFILE + "\.pyenv\pyenv-win\bin;" + $env:USERPROFILE + "\.pyenv\pyenv-win\shims;" + [System.Environment]::GetEnvironmentVariable('path', "User"),"User")
```

#### Usando diferentes versões com o Pyenv
É recomendado configurar o caminho de instalação da venv para o diretório do projeto

- Instalar uma nova versão do Python - `pyenv install versão-desejada`    
- Utilizar a versão instalada apenas no projeto - `pyenv local versão-desejada`

- Instalar as configurações do Poetry - `poetry install`

## Documentações
[python-poetry.org](https://python-poetry.org/docs/)

[earthly.dev/python-poetry](https://earthly.dev/blog/python-poetry/)

[pypi.org/pyenv-win](https://pypi.org/project/pyenv-win/#add-system-settings)

[github.com/pyenv-win](https://github.com/pyenv-win/pyenv-win)
## Vídeos de suporte
[How to Create and Use Virtual Environments in Python With Poetry](https://www.youtube.com/watch?v=0f3moPe_bhk)

[How to Use Poetry in Python to avoid Dependency Hell](https://www.youtube.com/watch?v=V5rKVrVhEh8&t=6s)

[How to Install and Run Multiple Python Versions on Windows 10/11 | pyenv & virtualenv Setup Tutorial](https://www.youtube.com/watch?v=HTx18uyyHw8)
