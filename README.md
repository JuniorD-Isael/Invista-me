# Invista-me

[![Updates](https://pyup.io/repos/github/JuniorD-Isael/Invista-me/shield.svg)](https://pyup.io/repos/github/JuniorD-Isael/Invista-me/) [![Python 3](https://pyup.io/repos/github/JuniorD-Isael/Invista-me/python-3-shield.svg)](https://pyup.io/repos/github/JuniorD-Isael/Invista-me/)

Sistema web para gerenciamento de investimentos, desenvolvido com Django e Bootstrap 5.

## Funcionalidades

- **Listagem** — Visualiza todos os investimentos cadastrados
- **Cadastro** — Adiciona novos investimentos com nome, valor, data e status de pagamento
- **Detalhes** — Visualiza informações detalhadas de um investimento
- **Edição** — Atualiza dados de investimentos existentes
- **Exclusão** — Remove investimentos com confirmação de segurança
- **Painel Admin** — Interface administrativa do Django para gerenciamento avançado

## Pré-requisitos

- Python 3.14+
- [Pipenv](https://pipenv.pypa.io/)

## Instalação e Configuração

1. Clone o repositório:

```bash
git clone https://github.com/JuniorD-Isael/Invista-me.git
cd Invista-me
```

2. Instale as dependências:

```bash
pipenv install
```

3. Crie o arquivo `.env` na raiz do projeto com as seguintes variáveis:

```env
SECRET_KEY=sua_chave_secreta_aqui
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
```

4. Execute as migrações do banco de dados:

```bash
pipenv run python manage.py migrate
```

5. Crie um superusuário para acessar o painel admin (opcional):

```bash
pipenv run python manage.py createsuperuser
```

6. Inicie o servidor de desenvolvimento:

```bash
pipenv run python manage.py runserver
```

Acesse a aplicação em [http://localhost:8000](http://localhost:8000)

## Estrutura do Projeto

```
Invista-me/
├── manage.py
├── Pipfile
├── Pipfile.lock
├── runtime.txt
├── Procfile
├── db.sqlite3
│
├── projeto_invista_me/          # Configuração do projeto Django
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
│
└── invista_me/                  # Aplicação principal
    ├── models.py                # Modelo de dados
    ├── views.py                 # Views (CRUD)
    ├── forms.py                 # Formulários
    ├── admin.py                 # Configuração do admin
    ├── apps.py
    └── templates/investimentos/ # Templates HTML
        ├── base.html
        ├── investimentos.html
        ├── novo_investimento.html
        ├── detalhes.html
        └── confirmar_exclusao.html
```

## Tecnologias Utilizadas

| Tecnologia | Versão | Descrição |
|------------|--------|-----------|
| [Python](https://www.python.org/) | 3.14 | Linguagem de programação |
| [Django](https://www.djangoproject.com/) | 6.1 | Framework web |
| [Bootstrap](https://getbootstrap.com/) | 5.0.2 | Framework CSS |
| [django-widget-tweaks](https://github.com/akmohtashami/django-widget-tweaks) | 1.5.1 | Renderização de formulários |
| [Whitenoise](https://whitenoise.evans.io/) | 6.12.0 | Serviço de arquivos estáticos |
| [dj-database-url](https://github.com/jazzband/dj-database-url) | 3.1.2 | Configuração de banco via URL |
| [python-decouple](https://github.com/henriquebastos/python-decouple) | 3.8 | Variáveis de ambiente |
| [SQLite](https://www.sqlite.org/) | — | Banco de dados (desenvolvimento) |

## Rotas Disponíveis

| Rota | Método | Descrição |
|------|--------|-----------|
| `/` | GET | Lista todos os investimentos |
| `/novo_investimento` | GET/POST | Formulário de criação |
| `/<id>` | GET | Detalhes do investimento |
| `/novo_investimento/<id>` | GET/POST | Formulário de edição |
| `/excluir_investimento/<id>` | GET/POST | Confirmação de exclusão |
| `/adm_junior` | GET | Painel administrativo Django |

## Modelo de Dados

### Investimento

| Campo | Tipo | Descrição |
|-------|------|-----------|
| `id` | BigAutoField | Identificador único (automático) |
| `investimento` | TextField | Nome do investimento |
| `valor` | FloatField | Valor investido |
| `pago` | BooleanField | Status de pagamento (padrão: `False`) |
| `data` | DateField | Data do investimento (padrão: data atual) |

## Contribuição

1. Faça um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b nova-feature`)
3. Faça commit das alterações (`git commit -m 'Adiciona nova feature'`)
4. Faça push para a branch (`git push origin nova-feature`)
5. Abra um Pull Request

## Licença

Este projeto não possui licença especificada.
