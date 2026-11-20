## Execução via Terminal
Estando na pasta do projeto "Workspaces/adk_workspace/my_first_agent_python"

### Crie o arquivo .env com base no exemplo
```sh
cat .env.example > .env
```

### Atuelize a Chave de API no .env
GOOGLE_API_KEY

### Ative as Variáveis de Ambiente
```sh
source .env
```

### Execute a Aplicação
```sh
python my_first_agent.py
```
