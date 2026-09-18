# ⚽ Football Brain 11x11 — Autonomous Football Simulation Engine

![HTML5](https://img.shields.io/badge/HTML5-Canvas%202D-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![AI](https://img.shields.io/badge/AI-Utility%20AI%20%26%20Multi--Agent-007ACC?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-1fcf78?style=for-the-badge)

O **Football Brain** é um motor de simulação de futebol 11x11 em Canvas 2D onde cada um dos 22 atletas atua como um agente autônomo dotado de inteligência artificial utilitária (*Utility AI*). Em vez de seguir scripts rígidos ou posições engessadas, os jogadores escaneiam o campo continuamente, interpretam linhas de passe, pesam riscos, disputam divididas físicas e tomam decisões contextuais em tempo real.

O projeto reúne física vetorial de atrito e inércia, condução de bola elástica dependente de habilidade técnica, sistema de torcida viva com impacto moral[cite: 3], cronômetro profissional com acréscimos dinâmicos[cite: 3], avaliação de notas ao vivo[cite: 3], replays em fita contínua[cite: 3] e disputa de pênaltis oficial[cite: 2, 3].

---

## 🌟 Principais Funcionalidades

* **22 Agentes com Utility AI:** Tomada de decisão contínua calculando pesos e utilidades para passes curtos, enfiadas, chutes a gol, condução ou dribles individuais[cite: 1, 3].
* **Física e Condução "Chiclete":** A bola é um corpo físico livre no gramado[cite: 1, 3]. Jogadores técnicos mantêm a bola colada ao pé em condução, enquanto mudanças bruscas de direção sob fadiga aumentam o risco de escape[cite: 1, 3].
* **Dribles Contextuais & Pivô de Centroavante:** Cortes secos para dentro ou em direção à linha de fundo, drible da vaca, proteção de bola e o clássico giro de 180° com finalização rápida do Homem de Área[cite: 1, 3].
* **Disputas Físicas Intensas (*Duels*):** Choques de corpo divididos onde força, antecipação, controle e velocidade definem quem fica com a posse[cite: 1, 3]. A bola espana para o espaço livre se nenhum atleta vencer a dividida[cite: 1, 3].
* **Torcida Viva (*Crowd System*):** Centenas de torcedores em partículas nas arquibancadas que vibram e piscam em tons luminosos a cada desarme, defesa ou gol, acelerando a recuperação de estamina do time apoiado[cite: 3].
* **Comemoração na Bancada:** Ao marcar um gol, o autor do tento corre até a arquibancada para festejar com a sua torcida, acompanhado pelo abraço dos companheiros[cite: 3].
* **Cronômetro com Ilusão de Tempo (45' + 45'):** Cada 2 segundos reais equivalem a 1 minuto no placar[cite: 3]. Paralisações, divididas e gols geram acréscimos reais com placa levantada pelo árbitro[cite: 3].
* **Transmissão Profissional:** Placar integrado na borda inferior, numeração clássica nas camisas (1 a 11), notas dinâmicas de 4.0 a 10.0, eleição do Craque do Jogo (*MOTM*) e Replay dos Gols[cite: 3].
* **Disputa de Pênaltis Oficial:** Em caso de empate no tempo normal, a partida move todos os atletas para o círculo central e inicia as cobranças alternadas na mesma baliza[cite: 2, 3].

---

## 🧠 Arquitetura de Inteligência Artificial

A cada ciclo mental, o motor de IA avalia o cenário ao redor do agente[cite: 1, 3].

### Funções Táticas Dinâmicas (*Tactical Roles*)
Mesmo partindo de sua posição base, o atleta assume papéis transitórios conforme a posse e a fase da jogada[cite: 1, 3]:

| Papel | Comportamento |
| :--- | :--- |
| `chaser` | O jogador mais próximo pressiona o portador da bola ou ataca uma bola viva[cite: 1, 3]. |
| `press` | Segunda onda de combate que encurta o setor para forçar o erro do rival[cite: 2, 3]. |
| `support` | Movimenta-se em ângulo diagonal para fornecer linha de passe limpa ao companheiro[cite: 1, 3]. |
| `runner` | Ataca as costas da defesa adversária respeitando a linha de impedimento[cite: 2, 3]. |
| `receiver` | Reconhece que a bola foi lançada para si e corre antecipadamente para o ponto futuro[cite: 1, 3]. |
| `link` | Volante que recua e oferece conexão entre defesa e meio-campo para circular a bola[cite: 1, 3]. |
| `cover` | Zagueiro central que guarda a profundidade e protege o centro da área[cite: 1, 3]. |
| `intercept` | Abandona a formação imediatamente para cortar uma bola longa de perigo iminente[cite: 1, 3]. |
| `salvar` | Arrancada de emergência para manter a bola viva dentro das quatro linhas[cite: 1, 3]. |

---

## ⚡ Mecânicas de Jogo e Física

### 1. Condução Chiclete & Erros de Domínio
O domínio e a condução da bola utilizam interpolação suave (*lerp*) atrelada à habilidade de **Controle** e **Drible**[cite: 1, 3]:
* Atletas habilidosos conduzem com toques curtos e alta retenção[cite: 1, 3].
* Corridas em velocidade máxima aliadas a curvas fechadas desgastam o controle, gerando perigo de perda de bola[cite: 1, 3].

### 2. Dribles no Mano a Mano & Pivô do 9
* **Extremos e Pontas:** Leem a postura corporal do marcador lateral[cite: 1, 3]. Se o zagueiro fecha a beirada, cortam para dentro em busca do pé bom para chute ou assistência na meia-lua[cite: 2, 3]; se o zagueiro cerca por dentro, aceleram até o fundo para o cruzamento[cite: 2, 3].
* **Centroavante Nato (Pivô 180°):** Ao receber de costas dentro da área, usa o corpo contra o marcador, gira em direção ao gol e chuta de primeira[cite: 3]. Caso o zagueiro antecipe o combate, a jogada resulta em desarme limpo[cite: 1, 3].

### 3. Disputas Físicas Divididas (*Duels*)
Quando dois adversários alcançam a bola juntos, o sistema aciona a dividida[cite: 1, 3]. O cálculo pondera **Força**, **Antecipação**, **Controle**, **Velocidade de Chegada** e a **Garra do Jogador**[cite: 1, 2, 3]. Se a dividida for muito equilibrada, a bola escorrega lateralmente para a disputa da segunda bola[cite: 1, 3].

### 4. Linha de Impedimento Real
O motor calcula continuamente a linha do penúltimo defensor adversário[cite: 2, 3]. Atacantes inteligentes temporizam sua corrida na mesma linha para não queimar a arrancada[cite: 2, 3]; passes efetuados para jogadores adiantados no instante do lançamento são anulados com tiro indireto[cite: 2, 3].

---

## 🏟️ Sistema de Torcida Viva e Fator Casa

Nas quatro laterais do estádio, centenas de pontos compõem as arquibancadas dos times Azul e Vermelho[cite: 3]:

* **Visual Reativo:** As torcidas vibram fisicamente e emitem pulsos luminosos coloridos em sincronia com o ritmo da partida[cite: 3].
* **Níveis de Vibração:**
  * *Cadenciado:* Troca de passes comum na defesa[cite: 3].
  * *Intenso:* Dribles concluídos, arrancadas no contra-ataque e defesas difíceis[cite: 3].
  * *Explosão / Frenesi:* No momento do gol, a torcida inteira da equipe autora entra em brilho neon contínuo com vibração máxima[cite: 3].
* **Impacto na Estamina:** Momentos de festa e pressão da torcida concedem bônus na recuperação de fôlego dos atletas em campo[cite: 3].
* **Força da Torcida (1 a 100):** Torcidas apaixonadas com força alta continuam vibrando e empurrando mesmo em situações de desvantagem no placar[cite: 3].
* **Fator Mandante:** O clube mandante ocupa a maior parte do estádio, recebe bônus de garra em disputas de bola e avança suas linhas de marcação com mais naturalidade[cite: 2, 3].

---

## ⏱️ Estrutura de Partida, Notas e Replay

### Relógio e Acréscimos Dinâmicos
* **90 segundos reais** por tempo representam **45 minutos** de futebol[cite: 3].
* Gols anotam automaticamente **+1 minuto** de acréscimo[cite: 3].
* Divididas prolongadas e paradas para atendimento somam frações de minutos, sinalizadas na placa de acréscimos luminosa[cite: 3].

### Notas em Tempo Real (4.0 a 10.0)
Todos os atletas iniciam avaliados em **6.0**[cite: 3]. Cada lance altera a nota:
* **Aumentam:** Gols (+1.5), Assistências (+1.0), Defesas difíceis (+0.6), Desarmes (+0.3), Dribles (+0.2) e Enfiadas de bola (+0.2)[cite: 3].
* **Reduzem:** Perda de posse no campo de defesa (-0.5), Gols sofridos (-0.3), Passes fáceis errados (-0.2) e Chutes isolados longe da meta (-0.2)[cite: 3].

### Craque do Jogo (*Man of the Match*)
Ao final da partida, o sistema analisa as estatísticas individuais e elege o Melhor em Campo, com cartão de honra destacando suas contribuições[cite: 3].

### Replay dos Gols (Memória de Fita)
O jogo armazena uma fita circular contínua gravando as coordenadas dos 22 jogadores e da bola[cite: 3]. Ao término da partida, botões interativos permitem rever os últimos 5 segundos que antecederam cada gol[cite: 3].

---

## 📋 Táticas e Formações

O simulador disponibiliza **7 esquemas táticos consagrados**[cite: 1, 3]:
* **4-3-3:** Amplitude com pontas abertos e triângulos de passe[cite: 1, 3].
* **4-4-2 Clássico:** Duas linhas compactas com ataque em dupla (Pivô + Profundidade)[cite: 1, 3].
* **3-5-2:** Alas avançados e meio-campo densamente ocupado[cite: 1, 3].
* **4-2-3-1:** Dupla de volantes de contenção com meia armador central[cite: 1, 3].
* **5-3-2:** Retranca baixa em linha de 5 e contra-ataques verticais rápidos[cite: 1, 3].
* **4-1-4-1:** Pressão alta com volante único na cobertura[cite: 1, 3].
* **4-3-1-2 Losango:** Domínio central por dentro e laterais com liberdade[cite: 1, 3].

### Instruções Setoriais em Tempo Real
Sem necessidade de reiniciar o jogo, é possível definir:
* **Zagueiros:** *Clássico / Linha* ou *Construtor* (avança para iniciar jogadas)[cite: 1, 3].
* **Laterais:** *Equilibrado*, *Ofensivo / Overlap* ou *Ficar na Defesa*[cite: 1, 3].
* **Volantes:** *Âncora* (protege a zaga) ou *Box-to-Box* (chega à área)[cite: 1, 3].
* **Meias:** *Pelas Pontas / Amplitude* ou *Pelo Centro / Jogo Interior*[cite: 1, 3].
* **Atacante:** *Homem de Área* (finalizador agressivo) ou *Falso 9* (recua para armar)[cite: 1, 3].

---

## 🎮 Controles e Atalhos

| Comando | Ação |
| :--- | :--- |
| **Clique / Toque no Jogador** | Abre o editor completo do atleta selecionado[cite: 1, 3]. |
| **Menu Superior de Seleção** | Permite selecionar instantaneamente qualquer um dos 22 jogadores[cite: 3]. |
| **ESPAÇO** | Pausa ou retoma o andamento da partida[cite: 1, 3]. |
| **D** | Ativa/desativa as linhas de depuração da IA (impedimento, trajetórias e alvos mentais)[cite: 1, 3]. |
| **R** | Reinicia o confronto e sorteia novos elencos[cite: 1, 3]. |

---

## 🧬 Arquétipos e DNA de Equipe

Os atletas são gerados através de arquétipos personalizados que influenciam atributos e tomadas de decisão[cite: 2, 3]:

* **Explosivo:** Velocidade pura e aceleração; perde rendimento em partidas longas[cite: 2, 3].
* **Técnico:** Domínio refinado, condução justa e passes milimétricos[cite: 2, 3].
* **Cerebral:** Visão de jogo superior, encontra enfiadas de bola com facilidade[cite: 2, 3].
* **Físico:** Implacável em divididas de corpo a corpo e proteção de bola[cite: 2, 3].
* **Incansável:** Estamina quase inesgotável e ritmo constante nos 90 minutos[cite: 2, 3].
* **Craque Frágil:** Habilidade genial com a bola, mas vulnerável a choques físicos[cite: 2, 3].
* **Vertical:** Transições velozes e busca constante pelo gol[cite: 2, 3].
* **Equilibrado:** Atributos consistentes em todas as fases de jogo[cite: 2, 3].

---

## 🚀 Como Executar o Projeto

O projeto possui **zero dependências externas**, construído exclusivamente com tecnologias web nativas.

1. Clone o repositório:
   ```bash
   git clone [https://github.com/seu-usuario/football-brain.git](https://github.com/seu-usuario/football-brain.git)
