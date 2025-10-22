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
