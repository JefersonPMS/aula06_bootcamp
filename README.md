# Configuração do Ambiente Virtual e Ferramentas de Desenvolvimento

## Passo a Passo

1. **Configurar o Ambiente Virtual com uv**:
   - Instale o **uv** (ferramenta rápida para gerenciamento de ambientes e pacotes):
     ```bash
     pip install uv
     ```
   - Crie um ambiente virtual:
     ```bash
     uv venv .venv
     ```
   - Ative o ambiente virtual:
     - **No PowerShell**:
       ```bash
       .\.venv\Scripts\Activate
       ```
     - **No Git Bash**:
       ```bash
       source .venv/Scripts/activate
       ```

2. **Instalar Dependências**:
   - Instale as dependências do projeto usando **uv**:
     ```bash
     uv pip install -r requirements.txt
     ```
   - Caso não tenha um arquivo `requirements.txt`, crie um com as dependências necessárias.

3. **Configurar o pre-commit**:
   - Instale o **pre-commit**:
     ```bash
     pip install pre-commit
     ```
   - Adicione o arquivo de configuração **.pre-commit-config.yaml** ao repositório (se ainda não tiver):
     ```yaml
     repos:
       - repo: https://github.com/psf/black
         rev: 23.9.1  # Use a versão mais recente
         hooks:
           - id: black

       - repo: https://gitlab.com/pycqa/flake8
         rev: 6.1.0   # Use a versão mais recente
         hooks:
           - id: flake8

       - repo: https://github.com/grantjenks/blue
         rev: 1.0.0   # Use a versão mais recente
         hooks:
           - id: blue
     ```
   - Instale os hooks do **pre-commit**:
     ```bash
     pre-commit install
     ```
   - Execute os hooks em todos os arquivos (opcional):
     ```bash
     pre-commit run --all-files
     ```
