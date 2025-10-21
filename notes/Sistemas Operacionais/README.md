# Fundamentos dos Sistemas Operacionais Modernos (DL)

> Introdução aos sistemas operacionais, seus conceitos, objetivos, funcionamento e principais tipos.

---

## Conceito

Um **sistema operacional (SO)** é um conjunto de programas que gerenciam os recursos do computador e facilitam sua utilização.  
Ele atua como uma **camada intermediária** entre o **hardware** e os **usuários ou programas**, controlando e otimizando o uso dos recursos disponíveis.

O SO pode ser visto como o **gerente do sistema**, responsável por organizar o uso de cada recurso e garantir que tudo funcione de forma eficiente e segura.

---

## Objetivos do Sistema Operacional

- **Oferecer recursos** do sistema de forma simples e acessível ao usuário.  
- **Gerenciar os recursos** existentes (memória, processador, armazenamento etc.) de modo eficiente.  
- **Garantir integridade e segurança** dos dados e dispositivos.  
- **Fornecer uma interface** que facilite a comunicação entre usuário e computador.

---

## Arquitetura de um Computador

### Unidade de Processamento Central (CPU)

- **Registradores:** memórias rápidas internas da CPU.  
- **Unidade de Controle (UC):** busca e interpreta instruções da memória.  
- **Unidade Lógica e Aritmética (ULA):** realiza operações matemáticas e lógicas.  
- **Contador de Programa (PC):** indica a próxima instrução a ser executada.

### Sistema de Memória Principal

Armazena **dados** e **instruções** que estão em uso pelo processador.

### Sistema de Entrada e Saída (E/S)

Controla a **entrada de dados** e a **saída de resultados**.  
Ciclo de execução:
1. O PC informa à UC qual instrução deve ser buscada.  
2. A UC busca a instrução na memória.  
3. A instrução é decodificada para que a ULA possa executá-la.  
4. Os dados são transferidos para os registradores.  
5. O resultado é armazenado na memória ou nos registradores.

---

## Arquitetura de Von Neumann

Modelo em que **dados e instruções compartilham a mesma memória**.  
É composto por **CPU, memória, dispositivos de entrada/saída e barramentos**.  
A CPU executa as instruções de forma sequencial: **buscar → decodificar → executar**.  
Esse modelo é a base dos computadores modernos.

---

## Tipos de Sistemas Operacionais

| Tipo | Descrição |
|------|------------|
| **Batch (Lote)** | Executa várias tarefas sem interação do usuário, aproveitando melhor o processador. |
| **De Rede** | Permite compartilhamento de recursos entre computadores conectados. |
| **Distribuído** | Conecta vários computadores para agir como um único sistema. |
| **Multiusuário** | Suporta acesso simultâneo de vários usuários com controle de permissões e segurança. |
| **Desktop** | Voltado para uso pessoal, com interface gráfica (ex: Windows, macOS, Linux). |
| **Servidor** | Gerencia grandes volumes de recursos e múltiplos usuários em rede. |
| **Embarcado** | Feito para dispositivos com poucos recursos (celulares, automação, IoT). |
| **Tempo Real** | Responde dentro de prazos previsíveis e rigorosos. <br> - *Soft real time:* atrasos reduzem desempenho. <br> - *Hard real time:* atrasos causam falhas críticas. |

---

## Programação Concorrente

Baseia-se na **execução simultânea e cooperativa** de vários processos ou threads.  

Seu objetivo é **melhorar o desempenho** e **aproveitar ao máximo os recursos do sistema**.

Sistemas com um processador < Sistemas com mais de um processador, pois, o com mais de um consegue realizar tarefas simultaneas em diferentes processadores.

---

## Comunicação por compartilhamento de memória

O compartilhamento da memória é um mecanismo que realiza a comunicação entre processos, usando uma área da memória > um buffer compartilhado entre vários processos de uma aplicação concorrente.

