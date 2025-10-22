# RESUMO — FUNDAMENTOS DE SISTEMAS OPERACIONAIS MODERNOS

## 1. Conceito e Função do Sistema Operacional (SO)
- **Definição:** Programa (ou conjunto deles) que atua como intermediário entre **usuário e hardware**.  
- **Função:** Gerenciar recursos do computador (CPU, memória, disco, dispositivos de E/S).  
- **Objetivos principais:**
  - **Conveniência:** Facilitar o uso do computador.  
  - **Eficiência:** Utilizar os recursos de forma otimizada.  
  - **Segurança e integridade:** Proteger dados e processos.  

**Autores importantes:**
- **Stallings (1992):** SO = interface entre usuário e hardware.  
- **Silberschatz (2001):** SO = ambiente intermediário.  
- **Tanenbaum (1995):** SO = programa que controla todos os recursos computacionais.  

---

## 2. Objetivos de um Sistema Operacional
1. Oferecer recursos do sistema de forma simples e transparente.  
2. Gerenciar recursos existentes (CPU, memória, disco, dispositivos).  
3. Garantir integridade e segurança dos dados.  
4. Prover interface (linha de comando → GUI).  

---

## 3. Evolução Histórica e Interfaces
- Primeiros SOs: comandos via texto (modo terminal).  
- Atuais: interfaces gráficas (GUI).  
- Importância: facilitar a interação humano-computador (IHC).  

---

## 4. Arquitetura de um Computador (Modelo de Von Neumann)
**Componentes principais:**
1. **CPU (Unidade de Processamento Central):**
   - Registradores: memória ultrarrápida interna.
   - UC (Unidade de Controle): busca e decodifica instruções.
   - ULA (Unidade Lógica e Aritmética): faz cálculos e comparações.
   - PC (Program Counter): indica a próxima instrução.
2. **Memória principal:** armazena dados e programas em execução.  
3. **Entrada e Saída (E/S):** dispositivos que recebem e exibem dados.  

**Ciclo de execução:**  
Buscar → Decodificar → Executar → Armazenar resultado.

---

## 5. Gargalo de Von Neumann
- Problema: CPU é mais rápida que a memória.  
- Consequência: CPU fica ociosa esperando dados.  
- Soluções modernas: cache, pipelines, memória RAM mais veloz.

---

## 6. Tipos de Sistemas Operacionais

| Tipo | Características | Exemplos |
|------|------------------|-----------|
| **Batch (Lote)** | Executa programas em fila, sem interação do usuário. | OS/360, VMS |
| **De Rede** | Compartilha recursos entre máquinas via rede. | Windows Server, Linux |
| **Distribuído** | Recursos de várias máquinas atuam como um só sistema. | Amoeba, Plan9 |
| **Multiusuário** | Vários usuários simultaneamente com segurança. | UNIX, Linux |
| **Desktop** | Voltado ao usuário final, interface gráfica. | Windows, macOS, Linux |
| **Servidor** | Gerencia recursos de rede e usuários. | Windows Server, Red Hat |
| **Embarcado** | Roda em hardware limitado. | Android, VxWorks, Symbian |
| **Tempo Real** | Respostas com tempo previsível. | QNX, RT-Linux, VxWorks |

---

## 7. Sincronização e Comunicação de Processos
- Programação concorrente: vários processos ou *threads* executando juntos.  
- Processos compartilham recursos → precisam de controle.  
- Sincronização: garante execução correta e sem conflitos.  
- Comunicação pode ser feita por:
  - Memória compartilhada (buffer).
  - Troca de mensagens.

**Regra:**
- Processo só escreve se o buffer não estiver cheio.  
- Processo só lê se houver dados disponíveis.  
- Caso contrário, fica em espera (estado bloqueado).  

---

## 8. Exclusão Mútua
- Garante que apenas um processo por vez acesse um recurso compartilhado.  
- Evita conflitos e inconsistências.  
- Trecho protegido = **Região Crítica**.  
- Situação problemática = **Condição de Corrida**.  

**Implementação (hardware):**
- Desabilitação de interrupções.  
- Instrução Test-and-Set.

---

## 9. Operações Atômicas
- Atômica: operação que não pode ser interrompida (executa toda de uma vez).  
- Não atômica: pode ser interrompida no meio.

| Operações Atômicas | Operações Não Atômicas |
|--------------------|------------------------|
| Tocar uma campainha | Encher um copo de refrigerante |
| Desligar um interruptor | Caminhar até a porta |
| Dar a ignição em um veículo | Tomar uma xícara de café |

- Fundamentais para sincronização e transações seguras.  

---

## 10. Mecanismos de Sincronização
- Garantem comunicação correta entre processos concorrentes.  
- Baseiam-se em operações atômicas.  
- Exemplo: processos que esperam o buffer estar livre ou cheio antes de agir.

---

## 11. Gerência de Memória
- Função: controlar o uso e a alocação da memória.  
- Responsável: Gerenciador de Memória do SO.

**Funções principais:**
- Controlar partes da memória usadas e livres.  
- Alocar espaço para processos.  
- Liberar espaço após a execução.  
- Fazer *swapping* (troca entre RAM e disco).

---

## 12. Unidade de Gerência de Memória (MMU)
- Hardware que traduz endereços lógicos → físicos.  
- Usa o Translation Lookaside Buffer (TLB) para acelerar o mapeamento.

---

## 13. Tipos de Gerenciamento de Memória

| Tipo | Descrição | Problemas |
|------|------------|-----------|
| **Monoprogramação** | Um único programa por vez. | Pouco eficiente. |
| **Multiprogramação (partições fixas)** | Divide memória em blocos fixos. | Fragmentação interna. |
| **Multiprogramação (partições variáveis)** | Tamanho das partições ajustável. | Fragmentação externa. |

---

## 14. Algoritmos de Alocação de Memória

| Algoritmo | Descrição |
|------------|------------|
| **First-fit** | Usa o primeiro espaço livre suficiente. |
| **Best-fit** | Usa o espaço mais ajustado ao tamanho do processo. |
| **Worst-fit** | Usa o maior espaço livre disponível. |
| **Next-fit** | Variante circular do First-fit. |

**Problemas:**
- Fragmentação interna (espaço desperdiçado dentro da partição).  
- Fragmentação externa (espaços vazios não contíguos).  
- Solução: compactação de memória (reorganizar os processos).  

---

## 15. Estruturas de Gerência de Memória

| Modo | Descrição |
|------|------------|
| **Mapa de bits** | Cada posição da memória tem um bit indicando livre/ocupada. |
| **Lista ligada** | Lista de regiões livres (H) e ocupadas (P). Mais eficiente. |

---

## 16. Conceitos-Chave que Mais Caem
- SO = intermediário entre usuário e hardware.  
- Objetivos: conveniência, eficiência e segurança.  
- Von Neumann: CPU + memória + E/S.  
- Gargalo: lentidão da memória frente à CPU.  
- Sincronização: processos cooperando corretamente.  
- Exclusão mútua: um processo por vez na região crítica.  
- Operações atômicas: indivisíveis e seguras.  
- Gerência de memória: alocação, swap, fragmentação, MMU.  
- Multiprogramação: melhora o uso da CPU.
