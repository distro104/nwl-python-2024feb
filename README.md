# nwl-python-2024feb
Projeto feito durante o evento da rocketseat utilizano a linguagem Python 


# Passos do Projeto

## Instalação e configuração do ambiente
### Virtualenv
Instalação: pip install virtualenv
Criando o ambiente virtual: python3 -m venv .venv
Ativar o ambiente virtual: source .venv/bin/activate

### Pylint
> Obs: A instalado deve ser feita com o ambiente virtual ja funcionando, tambem apos a instalação ser feita no projeto instalar a extenção referente ao mesmo no VSCode caso esteja sendo usado.

Instalação: pip install pylint

Criando o arquivo de definicoes: pylint --generate-rcfile > .pylintrc

Adicionando excessoes para que o pylint ignorar caso ocorram:
disable=
      C0114, # missing-module-docstring
      C0115, # missing-class-docstring
      C0116, # missing-function-docstring
      W0703, # catching too general exception Exception

Padronização adotada no desenvolvimento seguindo o Pylint:
snake_case -> Funções, Variaveis, Metodos
PascalCase -> Classes

### Pre-commit
Install: pip install pre-commit

Criar arquivo [.pre-commit-config.yaml]: cat > .pre-commit-config.yaml

Acidionar o conteudo no arquivo criado:
repos:
  - repo: local
    hooks:
      - id: pylint
        name: pylint
        entry: pylint
        language: system
        types: [python]
        args:
          [
            "-rn", # Only display messages
            "-sn", # Don't display the score
            "--rcfile=.pylintrc", # Link to your config file
            "--load-plugins=pylint.extensions.docparams", # Load an extension
          ]

Rodar o comando: pre-commit install


### Gerar arquivo [requirements.txt]
Obs: comando usado para gerar arquivo de configuracao onde sera listado todos os plugins utilizados no projeto.
Comando: .venv/bin/pip3 freeze > requirements.txt

### Instalar flask
comando: pip install Flask

### Instalar python bar code
Comando: pip install python-barcode

### Instalar Pillow
Comando: pip install pillow

>Obs: Sempre no final de todas as instalacoes deve se rodar o comando para gerar o arquivo de configuracao atualizado
Comando: .venv/bin/pip3 freeze > requirements.txt



# Links & References:
Virtualenv: 
https://pypi.org/project/virtualenv/

Configuração do ambiente virtual
https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/

PyLint:
https://pypi.org/project/pylint/

Pre-commit:
https://pre-commit.com/#install

Flask:
https://pypi.org/project/Flask/

Python bar code:
https://pypi.org/project/python-barcode/

Pillow:
https://pypi.org/project/pillow/