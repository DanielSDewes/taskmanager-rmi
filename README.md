# Task Management System (TaskManager) - RMI

## Visão Geral do Projeto
O Sistema de Gerenciamento de Tarefas (TaskManager) é uma aplicação distribuída construída utilizando Java RMI (Remote Method Invocation). O projeto permite que os clientes adicionem tarefas remotamente, as listem e as marquem como concluídas, tudo enquanto interagem com um servidor. O sistema é projetado para simular um gerenciador de tarefas básico, onde as tarefas podem ser adicionadas, listadas e atualizadas.

## Objetivo
O sistema permite que os clientes:

1. Adicionem tarefas
2. Listem tarefas
3. Marquem tarefas como concluídas

## Arquitetura
O projeto é dividido nos seguintes componentes:

Servidor: Implementa a lógica central de gerenciamento de tarefas.
Cliente: Fornece uma interface de console para interagir com o servidor.
Registro RMI: Registra o objeto remoto do servidor para que o cliente possa acessá-lo.
---

## Estrutura do projeto
```
📂 RMI_TaskManager/
┣ 📂 src/
┃ ┣ 📂 taskmanager/
┃ ┃ ┣ 📂 model/ 
┃ ┃ ┃ ┣ 📜 TaskManager.java  # Interface para os métodos remotos
┃ ┃ ┃ ┣ 📜 Task.java   # Modelo das tasks
┃ ┃ ┣ 📂 service/ 
┃ ┃ ┃ ┣ 📜 TaskManagerImpl.java  # Implementação da interface do task manager.
┃ ┃ ┃ ┣ 📜 TaskMainServer.java  # Ponto de entrada do server.
┃ ┃ ┃ ┣ 📜 TaskMainClient.java  # Ponto de entrada do cliente
```
### **taskmanager.model**

- **TaskManager.java**: Define a interface remota com os métodos adicionar, lista e marcar as tarefas como completas.
- **Task.java**: Contém a estrutura da task.

### **taskmanager.service**

- **TaskManagerImpl.java**: Implementa a interface `TaskManager`, contém para lógica para controlar as tarefas.
- **TaskMainServer.java**: O ponto de entrada para iniciar o server. Conecta o objeto `TaskManagerImpl` ao registro RMI.
- **TaskMainClient.java**: O ponto de entrada do client. Provém a interface de usuário para interagir com o server.

## How to Run the Project
1. **Compile the Java Files** (vá para pasta src)
```bash
    javac taskmanager/model/*.java taskmanager/service/*.java
```
2. **Iniciar o server**: Execute `java taskmanager.service.TaskMainServer`.
3. **Iniciar o rmiregistry**: Execute `start rmiregistry`.
4. **Iniciar o client**: Execute `java taskmanager.service.TaskMainClient`.
5. **Interagir com o client**: Use a interface na linha de comando para adicionar, listar e marcar as tarefas como completadas.

## Requirements

- **Java 8 or later**: Necessário para o RMI e classes do Java;
- **RMI Registry**: Garante que o registro do RMI está sendo executado no host.