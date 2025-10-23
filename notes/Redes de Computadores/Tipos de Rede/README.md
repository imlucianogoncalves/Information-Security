# Redes de Computadores, Tipos de Redes, Topologias e Cabeamento Estruturado

## 1. Redes de Dados — Conceito e Finalidade
- Redes de dados (ou redes de comunicação) surgiram para **compartilhar recursos de hardware e software** entre computadores.
- Antes das redes, computadores eram **isolados**, e a troca de arquivos era feita manualmente (ex: disquetes).
- Objetivo principal: **eficiência, economia e comunicação rápida** entre usuários e dispositivos.

---

## 2. Sneakernet — O Início da Conectividade
- Nos anos 1980, o compartilhamento era feito por **disquetes transportados manualmente** entre computadores.
- Essa prática era ineficiente:  
  - Criava várias cópias dos mesmos dados.  
  - Perdia informações quando dois usuários editavam o mesmo arquivo.  
- As empresas começaram a buscar **soluções automatizadas de rede**.

---

## 3. Evolução e Problemas Iniciais
- Cada empresa criava suas próprias tecnologias de rede (**arquiteturas proprietárias**).  
- As redes **não eram compatíveis entre si**, dificultando a comunicação entre sistemas diferentes.  
- Surgiu a necessidade de **padrões abertos** e **interconectividade**.

---

## 4. Solução: Redes Locais (LAN)
- As **LANs (Local Area Networks)** conectaram computadores dentro de um mesmo **departamento, prédio ou campus**.
- Permitiram o **compartilhamento de arquivos, impressoras e recursos de rede**.
- Estabeleceram **padrões abertos de comunicação**, permitindo compatibilidade entre equipamentos de diferentes fabricantes.

---

## 5. Limitação das LANs e Expansão das Redes
- Cada departamento funcionava como uma “ilha”: possuía sua própria rede, mas sem integração com outras.
- Com a expansão das empresas (filiais e escritórios remotos), as LANs tornaram-se insuficientes.
- Necessidade: **interligar várias LANs** e **compartilhar informações globalmente**.

---

## 6. Surgimento das Redes MAN e WAN
- **MAN (Metropolitan Area Network):** conecta redes dentro de uma mesma cidade ou área metropolitana.
- **WAN (Wide Area Network):** conecta redes de diferentes cidades, países ou continentes.
- As WANs possibilitaram a **comunicação entre filiais e empresas distantes**.
- **Internet** é o maior exemplo de uma **WAN global**.

---

## 7. Tipos de Redes por Alcance
| Tipo de Rede | Alcance | Exemplo | Nome Completo |
|---------------|----------|----------|----------------|
| **PAN** | Pessoal (até 10 m) | Bluetooth, smartwatch, celular | Personal Area Network |
| **LAN** | Local (até 1 km) | Redes de escritório, universidades | Local Area Network |
| **WLAN** | Local sem fio | Wi-Fi doméstico | Wireless Local Area Network |
| **MAN** | Metropolitana (até 100 km) | Redes de uma cidade | Metropolitan Area Network |
| **WAN** | Longa distância (acima de 100 km) | Internet, VPNs corporativas | Wide Area Network |

---

## 8. Mainframes — Computadores de Grande Porte
- **Mainframe:** computador de alto desempenho usado para **processar grandes volumes de dados**.
- Características:
  - Alta **performance**, **escalabilidade** e **segurança**.  
  - Suporte a múltiplos sistemas (Linux, Java, criptografia, IO de rede/disco).  
  - Usado em **bancos, governos e grandes corporações**.
- Tornou-se mais **compacto e eficiente** ao longo do tempo.

---

## 9. Questões que levaram à criação das redes modernas
As empresas buscavam resolver:
1. **Evitar duplicação de equipamentos e recursos.**  
2. **Melhorar a comunicação interna e externa.**  
3. **Facilitar a configuração e administração de redes.**

A partir disso, surgiram **redes integradas, eficientes e padronizadas.**

---

## 10. Topologias de Rede (Conceito)
As **topologias** definem a **forma como os dispositivos estão conectados** em uma rede.

### 10.1. Topologias Físicas
Descrevem **a estrutura real dos cabos e dispositivos**.

| Topologia | Características | Vantagens | Desvantagens |
|------------|-----------------|------------|---------------|
| **Barramento (Bus)** | Todos os dispositivos ligados em um único cabo principal. | Simples e barata. | Um erro no cabo pode afetar toda a rede. |
| **Anel (Ring)** | Dados circulam em um anel fechado. | Fluxo de dados ordenado. | Falha em um nó pode interromper a rede. |
| **Estrela (Star)** | Todos os dispositivos conectados a um **switch** ou **hub** central. | Fácil de gerenciar e expandir. | Ponto único de falha no equipamento central. |
| **Malha (Mesh)** | Cada dispositivo se conecta a todos os outros. | Alta redundância e confiabilidade. | Custo elevado. |
| **Árvore (Tree)** | Hierarquia de conexões em forma de galhos. | Escalável e organizada. | Complexa de configurar. |

### 10.2. Topologias Lógicas
Definem **como os dados trafegam** entre os dispositivos (independente do cabeamento físico).

| Tipo | Descrição | Exemplo |
|------|------------|----------|
| **Broadcast** | Todos os nós recebem a mensagem, mas só o destinatário a aceita. | Ethernet |
| **Token Passing** | Um “token” circula e dá permissão para transmitir dados. | Token Ring |

---

## 11. Cabeamento Estruturado
Sistema padronizado que **organiza toda a infraestrutura de cabos** de rede, voz e dados de um edifício.

### Componentes principais:
1. **Cabeamento horizontal:** conecta os pontos de rede até o painel de distribuição.  
2. **Cabeamento vertical (backbone):** interliga os andares ou blocos.  
3. **Armário de telecomunicações:** local onde os cabos são conectados e gerenciados.  
4. **Patch panels e racks:** organizam conexões.  
5. **Tomadas de rede (RJ-45)** e cabos **UTP, STP ou fibra óptica**.

### Benefícios:
- Organização e fácil manutenção.  
- Padrão universal (TIA/EIA-568).  
- Suporte a expansão e diferentes tecnologias (voz, dados, vídeo).

---

## 12. Principais Padrões de Cabeamento
| Categoria | Tipo de Cabo | Velocidade Máxima | Distância |
|------------|---------------|-------------------|------------|
| **Cat 5e** | Par trançado UTP | 1 Gbps | 100 m |
| **Cat 6** | Par trançado UTP/STP | 10 Gbps | 55 m |
| **Cat 6a** | Blindado (STP) | 10 Gbps | 100 m |
| **Fibra óptica** | Vidro ou plástico | 100 Gbps+ | Vários km |

---

## 13. Resumo dos Pontos que Caem em Prova

✅ **Redes de dados:** compartilhamento de recursos (hardware/software).  
✅ **Sneakernet:** origem das redes e suas limitações.  
✅ **Arquiteturas proprietárias:** falta de compatibilidade entre redes antigas.  
✅ **LAN / MAN / WAN / PAN / WLAN:** classificação das redes por alcance.  
✅ **Mainframe:** computador de grande porte, alta performance e segurança.  
✅ **Topologias físicas e lógicas:** estrutura e fluxo de dados na rede.  
✅ **Cabeamento estruturado:** organização e padronização da infraestrutura.  
✅ **Categorias de cabos e padrões TIA/EIA-568.**

---

## 14. Dica de Memorização Rápida

| Tema | Palavra-Chave | Lembre-se |
|------|----------------|-----------|
| **LAN** | Local | Rede de escritório ou campus |
| **MAN** | Metropolitana | Rede de cidade |
| **WAN** | World | Rede global (Internet) |
| **Topologia Estrela** | Centralização | Switch ou hub principal |
| **Cabeamento Estruturado** | Organização | Facilita manutenção |
| **Mainframe** | Desempenho | Grandes volumes de dados |

---

## 15. Conclusão
As redes evoluíram do **isolamento dos computadores individuais** para **infraestruturas interconectadas globais**, integrando pessoas, dados e sistemas com **eficiência, segurança e padronização**.

Hoje, o conhecimento sobre **tipos de redes, topologias e cabeamento estruturado** é essencial para compreender **como a comunicação digital é organizada e mantida** em qualquer ambiente corporativo.
