# Compartilhamento de Memória e Processos Concorrentes

## 1. O que é o Compartilhamento de Memória
Em sistemas operacionais **multiprogramados** (vários processos rodando ao mesmo tempo), pode acontecer de dois ou mais processos precisarem trocar informações.

Uma das formas mais eficientes de fazer isso é o **compartilhamento de memória**.

### Conceito
O **compartilhamento de memória** é quando dois ou mais processos **acessam a mesma área da memória RAM**, chamada de **buffer compartilhado**.  
- Um processo **escreve dados** no buffer.  
- Outro processo **lê esses dados**.

Essa troca é direta, sem passar por arquivos ou rede.

---

## 2. Problemas que Podem Ocorrer
O desafio é que **dois processos podem tentar usar o mesmo espaço ao mesmo tempo**, gerando **inconsistências**.

### Exemplo:
Imagine um buffer onde o **Processo A (produtor)** coloca dados e o **Processo B (consumidor)** lê.  
- Se o **A** tentar escrever enquanto o buffer está cheio → ele precisa **esperar**.  
- Se o **B** tentar ler quando o buffer está vazio → ele também **espera**.  

Essas regras são garantidas por **mecanismos de sincronização**.

---

## 3. Sincronização
### Definição
É o **controle da ordem de execução** entre processos que compartilham recursos, para evitar conflitos.

O **sistema operacional** implementa a sincronização para:
- Evitar que dois processos usem o mesmo recurso ao mesmo tempo.
- Garantir que cada processo leia e grave dados corretamente.

Quando um processo **espera** o outro terminar para acessar o recurso, dizemos que ele está em **estado de espera (bloqueado)**.

---

## 4. Exclusão Mútua
### O que é
É o mecanismo que **impede acesso simultâneo** de dois ou mais processos a um mesmo recurso.

> Só **um processo por vez** pode acessar a “região crítica”.

### Região Crítica
É o **trecho do código** onde o processo acessa um recurso compartilhado (por exemplo, uma variável, arquivo ou buffer).

### Exemplo
Dois processos atualizando o saldo da mesma conta bancária.  
Se um altera o valor enquanto o outro lê, o saldo pode ficar incorreto.

Com **exclusão mútua**, um processo entra na região crítica, executa, e **só depois** o outro pode entrar.

### Como é Implementada
1. **Por software:** usando algoritmos de controle (como Peterson ou Dekker).  
2. **Por hardware:** com instruções especiais como `test-and-set` ou desabilitação de interrupções, que bloqueiam o acesso de outros processos enquanto um estiver executando.

---

## 5. Condição de Corrida
### Conceito
A **condição de corrida** ocorre quando dois processos **acessam e modificam o mesmo recurso** ao mesmo tempo, e o resultado **depende da ordem** de execução.

**Exemplo:**
Processo 1: A = B + 1
Processo 2: B = 2 × B


Dependendo de quem executar primeiro, o valor final de A e B muda.  
A exclusão mútua evita esse tipo de erro.

---

## 6. Operações Atômicas
### Conceito
Uma **operação atômica** é uma ação que o processador executa **inteira de uma vez**, sem interrupções.  
Não existe “meio termo” — ou ela é feita completamente, ou não é feita.

### Exemplo (do dia a dia)
- **Atômico:** Tocar uma campainha (não dá pra tocar “pela metade”).  
- **Não atômico:** Encher um copo de refrigerante (pode ser interrompido no meio).

### Importância
Em programação concorrente, operações atômicas são essenciais para **sincronização**.  
Exemplo: incrementar uma variável compartilhada deve ser atômico (`x = x + 1`) — senão dois processos podem tentar alterar ao mesmo tempo e o resultado será incorreto.

### No Hardware
O processador fornece instruções **atômicas** (como `test-and-set`, `compare-and-swap`, `xchg`) que garantem que uma operação aconteça **sem interferência de outros processos**.

---

## 7. Mecanismos de Sincronização
São **ferramentas do sistema operacional** (ou da linguagem de programação) para controlar o acesso aos recursos compartilhados.

### Principais Mecanismos
- **Semáforos:** contadores que indicam se um recurso está livre ou ocupado.  
- **Mutex (Mutual Exclusion Object):** permite acesso exclusivo de um processo por vez.  
- **Monitores:** estruturas de alto nível que encapsulam variáveis compartilhadas e funções seguras.  

Esses mecanismos usam **operações atômicas** para garantir que o controle de acesso não cause novas condições de corrida.

---

## 8. Gerência de Memória
O **Sistema Operacional** precisa controlar **quais partes da memória estão sendo usadas**, **por quem**, e **quando liberar**.

### Principais Funções
1. **Alocação:** escolher onde cada processo vai ser colocado na memória.  
2. **Liberação:** remover processos finalizados e liberar o espaço.  
3. **Proteção:** evitar que um processo leia/escreva na área de outro.  
4. **Swapping:** mover processos entre memória principal (RAM) e disco, para liberar espaço.  

---

## 9. Unidade de Gerência de Memória (MMU)
A **MMU (Memory Management Unit)** é um **hardware** que traduz os endereços **lógicos (virtuais)** dos programas em **endereços físicos (reais)** na memória RAM.

Ela faz esse mapeamento através de uma tabela de páginas (Page Table), e usa uma memória cache chamada **TLB (Translation Lookaside Buffer)** para acelerar a tradução.

---

## 10. Tipos de Gerenciamento de Memória

| Tipo | Características | Problema |
|------|------------------|-----------|
| **Monoprogramação** | Apenas um programa na memória por vez. | Ineficiente. |
| **Multiprogramação (partições fixas)** | Divide a memória em blocos de tamanhos fixos. | Fragmentação interna (espaço desperdiçado dentro da partição). |
| **Multiprogramação (partições variáveis)** | Partições criadas sob demanda, com tamanho ajustável. | Fragmentação externa (espaços vazios não contíguos). |

---

## 11. Algoritmos de Alocação de Memória

| Algoritmo | Descrição |
|------------|------------|
| **First-Fit** | Aloca o primeiro espaço livre suficiente. |
| **Best-Fit** | Escolhe o espaço mais justo para o processo (menor sobra). |
| **Worst-Fit** | Usa o maior espaço livre disponível. |
| **Next-Fit** | Variante do First-Fit, continua de onde parou a última busca. |

### Fragmentação
- **Interna:** espaço desperdiçado *dentro* da partição.  
- **Externa:** sobras *entre* partições ocupadas.  
**Solução:** compactação de memória (mover processos para juntar espaços livres).

---

## 12. Representação de Espaços de Memória

| Modo | Descrição |
|------|------------|
| **Mapa de Bits** | Cada posição da memória é representada por 1 bit (0 = livre, 1 = ocupada). Simples, mas pode ser lento. |
| **Lista Ligada** | Regiões livres e ocupadas são mantidas em uma lista (P = processo, H = espaço livre). Mais eficiente e flexível. |

---

## 13. Conceitos-Chave de Memória e Concorrência
- **Processos concorrentes:** executam em paralelo, compartilham recursos.  
- **Buffer compartilhado:** espaço comum usado para troca de dados.  
- **Sincronização:** garante ordem e consistência.  
- **Exclusão mútua:** impede acesso simultâneo à região crítica.  
- **Operações atômicas:** indivisíveis e seguras.  
- **MMU:** converte endereços virtuais em físicos.  
- **Multiprogramação:** permite vários processos na memória ao mesmo tempo.  
- **Fragmentação:** desperdício de espaço (interna ou externa).  

---

## Resumo Final
A partir do compartilhamento de memória, tudo no sistema operacional gira em torno de **coordenar processos que trabalham juntos**, garantindo que **não interfiram uns nos outros**, e que o **uso da memória seja eficiente e seguro**.
s