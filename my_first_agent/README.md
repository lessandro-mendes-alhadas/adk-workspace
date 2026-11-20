## Execução via Terminal
### Estando na pasta do workspace "Workspaces/adk_workspace"
```sh
adk run my_first_agent
```

### Estando na pasta do agent "Workspaces/adk_workspace/my_first_agent"
```sh
adk run .
```
Daí, basta digitar o prompt.

## Execução via servidor de API
### Estando na pasta do workspace "Workspaces/adk_workspace"
```sh
adk api_server my_first_agent
```

### Estando na pasta do agent "Workspaces/adk_workspace/my_first_agent"
```sh
adk api_server .
```

### Acessar /docs
Acesse http://127.0.0.1:8000/docs

## Interar no modo api_server
Primeiro deve-se criar uma sessão para um usuário
```sh
curl -X POST http://127.0.0.1:8000/apps/{app_name}/users/{user_id}/sessions
```

Exemplo
```sh
curl -X POST http://127.0.0.1:8000/apps/my_first_agent/users/student_1/sessions/session_1
```

## Executa utilizando usuário e sessão
```sh
curl -X POST http://127.0.0.1:8000/run \
  -H "Content-Type: application/json" \
  -d '{
    "appName": "my_first_agent",
    "userId": "student_1",
    "sessionId": "session_1",
    "newMessage": {
      "role": "user",
      "parts": [{"text": "What is 2x + 5 = 13?"}]
    }
  }'
```