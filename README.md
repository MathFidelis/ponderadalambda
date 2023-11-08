# AWS Lambda + API Gateway Endpoint

Este documento fornece uma visão geral de como implementar e testar uma função AWS Lambda com um endpoint HTTP criado através do AWS API Gateway.

## Implementação da Função Lambda

### Pré-requisitos

- Conta AWS com permissões de administrador.
- [AWS CLI](https://aws.amazon.com/cli/) configurado com as credenciais da sua conta AWS.

### Passos

1. **Código da Função Lambda**: Escreva o código para a função Lambda e salve-o em um arquivo chamado `lambda_function.py`. Certifique-se de que você tenha uma variável de ambiente `AUTH_TOKEN` configurada dentro do seu código:

2. **Subir para a AWS**:
    - Use o AWS CLI ou a AWS Management Console para criar ou atualizar sua função Lambda com o código acima.
    - Configure a variável de ambiente `AUTH_TOKEN` na seção de configuração de ambiente da função Lambda.

## Configuração do API Gateway

### Passos

1. **Adicionar Gatilho**: No console da função Lambda, adicione um gatilho selecionando o API Gateway.
2. **Criar API**: Opte por uma nova API HTTP API ou REST API, conforme necessário.
3. **Definir Segurança**: Escolha a opção de segurança (para testes iniciais, pode-se optar por nenhuma segurança).
4. **Deploy**: Crie um novo recurso e método, e faça o deploy da API em um estágio.

## Testando o Endpoint

### Endpoint
endpoint: https://yxwy8cuxr3.execute-api.us-east-1.amazonaws.com/default/Funcao
### Testes
#### Mensagens
```json
{
"body": "{\"email\": \" aaa@gmail\", \"kg\": 90, \"apelido\": \"Lil N\"}"
}
````
#### Testes Unitários
- Autenticação aprovada
<br><br>
<img width="658" alt="image" src="https://github.com/MathFidelis/ponderadalambda/blob/main/Screenshot%202023-11-08%20133022.png">
<br><br>
- Autenticação rejeitada
<br><br>
<img width="572" alt="image" src="https://github.com/MathFidelis/ponderadalambda/blob/main/Screenshot%202023-11-08%20133506.png">
<br><br>
- Autenticação ausente
<br><br>
<img width="643" alt="image" src="https://github.com/RodrigoMMartins1/ATIVIDADE_PROGRAMACAO_POST/assets/99209230/16cea17d-df08-45bd-ac1b-36d6ba4f7a9f">
<br><br>
- Autenticação aprovada, porém JSON não valido
<br><br>

