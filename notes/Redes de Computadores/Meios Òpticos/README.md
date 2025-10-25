# Meios ópticos

A fibra óptica transmite dados por meio de pulsos de luz que viajam dentro do núcleo do cabo.

A fibra tem 3 camadas principais:

1. Núcleo: por onde a luz se propaga.
2. Revestimento interno: mantém a luz refletindo dentro do núcleo.
3. Revestimento externo (buffer): protege toda a estrutura.

---

## Entrada da Luz

A luz só entra no núcleo se o ângulo de incidência estiver dentro da abertura numérica (NA) da fibra.

Se o ângulo for muito grande ou muito pequeno, o raio não é refletido corretamente e escapa da fibra.

---

## Modos de Propagação

Depois de entrar na fibra, a luz pode seguir diferentes caminhos dentro do núcleo.
Esses caminhos são chamados de modos de propagação.

---

## Tipos de Fibra

### Multimodo:

- Núcleo maior.

- Permite vários caminhos para a luz.

- Ideal para curtas distâncias (maior dispersão).

### Monomodo:

- Núcleo muito pequeno.

- Permite apenas um caminho da luz.

- Ideal para longas distâncias (sinal mais limpo e rápido).

## Estrutura interna

O cabo de fibra óptica é composto por cinco partes:

- Núcleo.
- Revestimento interno.
- Buffer.
- Um material reforçante.
- Capa externa.

### Revestimento interno

- Localizada ao redor do núcleo.
- Índice de refração menor.
- Faz a luz refletir e permanecer dentro do núcleo, caso tente sair.

*OBS: Em residências, o tipo de cabo utilizado como padrão é o cabo de fibra óptica multimodo.*

### Buffer

- Fica em volta do revestimento interno
- Ajuda a proteger tanto o núcleo quanto o revestimento interno contra danos.

### Formatos de cabo de fibra óptica

- Loose-tube: usado para a parte externa de ambientes.
- Tight-buffer: usado para a parte interna de ambientes (mais usada em residências)

## Cabo de fibra óptica loose-tube (tubo solto)

- A fibra se mover dentro do cabo.
- Evita pontos de estresse localizados (em curvas por ex)
- Impede microdobras
- Perde pouca intensidade de sinal (baixa atenuação)

## Cabo de fibra óptica tight-buffered

- O buffer é aplicado diretamente sobre a fibra
- A fibra é presa ao cabo, fixa.
- Bem resistente a altos impactos
- Resistente a abrasões
- Ela é menor.

---

A fibra de aramida é bem resistente e leve, cor amarelada e comumente conhecida como Kevlar.

---

## Foto emissores

- LEDs infrared: mais baratos, menos preocupação com segurança 
- Laser VCSELs: maior distância de entrega (até 2.000m)

## Fibras ópticas monomodo

Permitem apenas um modo de luz se propagando pelo núcleo da fibra óptica.

Um laser inframermelho é usado como fonte de luz, entrando em um raio de 90 graus, o que resulta na luz transmitida em linha reta - o que aumenta a velocidade e a distância que os dados podem ir.

Monomodo:

- Até 3.000 metros

Multimodo:

- Aproximadamete 2.000 metros.

Aparência:

- Núcleo da fibra monomodo é bem mais fino, por isso envia dados mais longe e mais rápido

- Custo de fabricação maior.

---

## Redes sem fios

Para garantir que diversos equipamentos de diferentes fabricantes consigam comunicar-se entre sí, foram criados padrões de uso das redes para garantir a interoperalidade.

Eles definem como os dados:

- São transmitidos
- Codificados
- Recebidos

Assim evitamos conflitos e incompatibilidade. 

A IEEE é uma das principais fontes de criação de tais padrões.


## DSSS (Direct Sequence Spread Spectrum)
- Tecnologia do padrão IEEE 802.11 para redes sem fio.  
- Opera entre 1 e 2 Mbps (padrão original), podendo chegar a 11 Mbps.  
- Espalha o sinal em uma faixa larga de frequência → menor interferência.  
- Base do padrão 802.11b.  

---

## Padrão 802.11b
- Também chamado de Wi-Fi™.  
- Usa DSSS.  
- Velocidades: 1, 2, 5.5 e 11 Mbps.  
- Retrocompatível com 802.11 (1 e 2 Mbps).  
- Permite atualizar a rede sem trocar hardware.  

---

## Padrão 802.11a
- Opera em 5 GHz.  
- Velocidade: até 54 Mbps (108 Mbps em versões proprietárias).  
- Não compatível com 802.11b (frequências diferentes).  
- Menor alcance, mas menos interferência.  

---

## Padrão 802.11g
- Opera em 2,4 GHz, como o 802.11b.  
- Velocidade: até 54 Mbps.  
- Usa OFDM (Orthogonal Frequency Division Multiplexing).  
- Retrocompatível com 802.11b.  

---

## Comparativo Rápido

| Padrão | Frequência | Velocidade | Tecnologia | Compatibilidade |
|--------|-------------|-------------|-------------|----------------|
| 802.11 | 2,4 GHz | 2 Mbps | DSSS / FHSS | — |
| 802.11b | 2,4 GHz | 11 Mbps | DSSS | 802.11 |
| 802.11a | 5 GHz | 54 Mbps | OFDM | — |
| 802.11g | 2,4 GHz | 54 Mbps | OFDM + DSSS | 802.11b |

---

- Wi-Fi 6 = Padrão IEEE 802.11ax.  
- É a nova geração do Wi-Fi, sucessora do 802.11ac (Wi-Fi 5).  
- Focado em maior eficiência, velocidade e capacidade.  

---

## Principais Características
- Mais rápido que o Wi-Fi 5.  
- Mais eficiente: permite que mais dispositivos usem a rede sem lentidão.  
- Mais estável: mantém desempenho mesmo em ambientes com muitos usuários.  
- Une:
  - Velocidade da conexão Gigabit Ethernet, e  
  - Confiabilidade das comunicações por rádio licenciado.  

---

## Benefícios
- Suporta novas aplicações (como IoT, streaming 4K, jogos online).  
- Melhora o desempenho de aplicações antigas.  
- Maior capacidade por área — ideal para locais com muitos dispositivos (empresas, escolas, aeroportos).  
- Mais previsibilidade e qualidade de serviço (QoS).  

## Topologias e dispositivos para redes sem fios  

Com uma simples placa de rede sem fio — seja onboard (integrada à placa-mãe) ou offboard (instalada separadamente) — é possível criar uma conexão de rede sem fio.

Entretanto, esse tipo de rede costuma ter baixa segurança, e algumas placas de rede podem apresentar problemas de compatibilidade com os diferentes padrões IEEE 802.11a, 802.11b e 802.11g.

Para solucionar essas limitações, utiliza-se um ponto de acesso (AP – Access Point), um dispositivo projetado para suportar múltiplos padrões Wi-Fi e garantir maior compatibilidade e estabilidade.

O Access Point atua como um hub central, concentrando e gerenciando toda a comunicação entre os dispositivos conectados à rede sem fio.

Esse Access Point, é conectado a partir de fios na rede local cabeada para fornecer acesso à internet e conectividade.

**OBS: Backbone é a espina dorsal da rede, é o cabo que irá servir de conexão para todas os routers, swtiches, aps.**

**OBS2: É recomendado ter uma sobreposição de 20% a 30%, pra evitar interrupção na conexão**

---

Quando ligamos o Wi-Fi em nossos dispoitivos, inicia-se o processo de varredura que pode ser tanto ativo quanto passivo.

- Passivo: fica ouvindo e os APs enviam beacons com as informações.
- Ativo: envia mensagens de busca chamada com o SSID (nome da rede) que ele quer encontrar.

Na passiva, o nó pode ser um celular, pc, notebook, uma vez que ele escuta e um AP responde com o BSSID de interesse do nó, ele envia a solicitação de conexão.

---