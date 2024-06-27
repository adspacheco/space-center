# Início de Projeto Django

1.  **Definir a versão local do Python:** Utilize o `pyenv` para definir a versão do Python a ser usada no projeto. No exemplo, a versão especificada é a 3.12.4:

    ```bash
    pyenv local 3.12.4
    ```
2.  **Criar um ambiente virtual:** Use o módulo `venv` para criar um ambiente virtual dentro do diretório do projeto:

    ```bash
    python -m venv .venv
    ```
3.  **Ativar o ambiente virtual:** Ative o ambiente virtual para garantir que todas as dependências sejam instaladas isoladamente do sistema principal:

    ```bash
    source .venv/bin/activate
    ```
4.  **Verificar as dependências instaladas:** Utilize o comando `pip freeze` para listar todas as dependências instaladas atualmente:

    ```bash
    pip freeze
    ```
5.  **Atualizar o `pip`:** Garanta que você está utilizando a versão mais recente do `pip`:

    ```bash
    pip install --upgrade pip
    ```
6.  **Instalar o `pip-tools`:** O `pip-tools` é uma ferramenta útil para gerenciar as dependências do projeto:

    ```bash
    pip install pip-tools
    ```
7.  **Verificar a instalação do `pip-compile`:** Verifique se o `pip-compile` está sendo executado a partir do ambiente virtual. Se não estiver, reative o ambiente virtual:

    ```bash
    which pip-compile
    # Para reativar, caso necessário
    source .venv/bin/activate
    ```
8.  **Criar um arquivo `.gitignore`:** Utilize o `ignr` para gerar um `.gitignore` específico para projetos Python e PyCharm:

    ```bash
    ignr -p python pycharm > .gitignore
    ```
9.  **Criar o arquivo `requirements.in`:** Edite o arquivo `requirements.in` para adicionar as dependências desejadas, como por exemplo, o Django:

    ```bash
    vim requirements.in
    # Adicione a linha "Django" dentro do arquivo
    ```
10. **Compilar as dependências:** Utilize o `pip-compile` para gerar o arquivo `requirements.txt` com todas as dependências resolvidas e suas versões específicas:

    ```bash
    pip-compile
    ```
11. **Criar o arquivo README.md:** Crie um arquivo `README.md` para documentar o projeto:

    ```bash
    echo "# projeto" > README.md
    ```
12. **Inicializar o repositório Git:** Inicie o repositório Git localmente e adicione todos os arquivos:

    ```bash
    git init
    git add .
    git commit -m "first commit"
    ```
13. **Criar o repositório no GitHub:** Crie um repositório em branco no GitHub e adicione o repositório remoto:

    ```bash
    git branch -M main
    git remote add origin git@github.com:user/repo.git
    git push -u origin main
    ```
