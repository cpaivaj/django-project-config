# Configurando ambiente Django (Linux Ubuntu)

## Ambiente Virtual:
python -m venv myvenv

## Caso não tenha venv instalado:
sudo apt install python-venv

## Ativando o Ambiente Virtual:
source myvenv/bin/activate

## Instalação do Django e dependências iniciais:

### Atualização pip, caso necessário:
python -m pip install --upgrade pip

### Pacotes e requisitos
Crie um arquivo na raiz chamado 'requirements.txt'

(projeto/requirements.txt)

### Adicione as dependências dentro do arquivo:
Django~=2.2.2 (Versão que deseja instalar)

### Instalando as dependências
pip install -r requirements.txt

# Iniciando o Projeto
django-admin startproject NOME_DO_PROJETO .

### Precisa usar o . para criar no diretório atual, se não usar será criado outro diretório
(projeto/projeto/arquivos...) - Não queremos assim :(

(projeto/arquivos...) - queremos assim :D

## Settings.py
<pre><code>
  TIME_ZONE = 'America/Sao_Paulo'
  LANGUAGE_CODE = 'pt-BR'
  STATIC_URL = '/static/'
  STATIC_ROOT = os.path.join(BASE_DIR, 'static')

  DATABASES = {
     'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db_sqlite3'),
     }
  }
</code></pre>

## Criação do banco e tabelas padrão
python manage.py migrate

# Criar aplicações

python manage.py startapp NOME_DA_APP

## Adicionar app ao settings.py
<pre><code>
INSTALLED_APPS = [
  'django.contrib.admin',
  ...
  ...
  ...
  ...
  'NOME_DA_APP',
 ]
</code></pre>

# Usuário administrador
python manage.py createsuperuser

localhost:8000/admin

# Pronto! Missão cumprida!!!

python manage.py runserver (localhost:8000)
