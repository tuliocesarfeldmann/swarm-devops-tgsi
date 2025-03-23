# Projeto de Implantação GitOps com Docker Swarm e Microsserviços Financeiros

Este repositório contém a configuração necessária para executar o sistema de microsserviços financeiro disponível em [sistema-microsservicos-demo](https://github.com/tuliocesarfeldmann/sistema-microsservicos-demo) em um cluster Docker Swarm.

## Estrutura do Repositório

```
├── devops-tgsi-swarm
```

### Arquivo `docker-compose.yml`
Este arquivo define os serviços necessários para o sistema de microsserviços, incluindo:

- **gateway**: Responsável por receber requisições REST e publicá-las nas filas correspondentes.
- **consulta**: Inscrito na fila `queue-consult-rabbit`, processa requisições de consulta.
- **saque**: Inscrito na fila `queue-cash-withdrawal-rabbit`, processa requisições de saque.
- **redis**: Armazena informações temporárias entre as requisições.
- **rabbitmq**: Sistema de mensageria que intermedia a comunicação entre os microsserviços.

## Requisitos

- Docker
- Docker Swarm configurado e iniciado

## CD - Continuous Deployment

Alterações mescladas com a main acionam o gatilho para a Action que atualiza o cluster Swarm.

## Como Parar os Serviços

Para remover a stack do Docker Swarm, execute:
```bash
docker stack rm sistema-financeiro
```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias.

