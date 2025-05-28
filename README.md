# 🤖 Projeto EV3 - Navegação Autônoma com Sensores   
Este projeto utiliza o LEGO Mindstorms EV3 com o sistema ev3dev e a biblioteca pybricks para permitir a navegação autônoma de um robô dentro de um ambiente pré-definido. O robô usa sensores para detectar obstáculos, bordas no chão e ajustar sua rota dinamicamente, garantindo uma movimentação eficiente e precisa.

-----

## 📌 Objetivo  
O robô deve se deslocar dentro de um grid tomando decisões de movimento com base nas leituras dos sensores, garantindo uma navegação eficiente e segura. Para isso, ele conta com a capacidade de evitar obstáculos utilizando análise lateral, permitindo ajustes automáticos de rota sempre que necessário. Além disso, possui um sistema de recalibração para corrigir possíveis desalinhamentos, garantindo uma trajetória precisa. O seguimento de linha e o controle PID aprimoram a fluidez dos movimentos, tornando as curvas mais suaves e controladas. O display do EV3 exibe informações em tempo real sobre a posição do robô, facilitando o monitoramento da navegação. Por fim, o robô registra e armazena os caminhos percorridos, permitindo o mapeamento de rotas e a otimização dos deslocamentos futuros. 🚀🤖

-----

## 🧠 Funcionalidades
**🔹 Movimentação precisa com DriveBase**
O EV3Brick controla dois motores, garantindo movimentação fluida dentro do grid, utilizando funções de avanço, rotação e recalibração.

**🔹 Detecção de obstáculos e escolha de rota alternativa**
O sensor ultrassônico mede distâncias e, ao detectar um obstáculo, o robô analisa lateralmente antes de decidir virar à esquerda ou à direita.

**🔹 Seguimento de linha**
O sensor de cor permite que o robô identifique mudanças no solo e faça ajustes precisos, evitando quedas e movimentos inesperados.

**🔹 Recalibração automática**
Se o sensor giroscópio detectar desalinhamento, o robô recuará e avançará novamente para corrigir a posição.

**🔹 Visualização gráfica da posição**
O display do EV3 exibe mensagens com leituras dos sensores, garantindo feedback em tempo real sobre navegação e correções.

**🔹 Mapeamento inteligente do caminho**
O código armazena rotas percorridas, permitindo ajustes e otimização na movimentação.

-----

## 🛠️ Componentes Utilizados
**Motores**  
- Motor Esquerdo → Porta D  
- Motor Direito → Porta A  
- Motor do Sensor Ultrassônico → Porta B
  
**Sensores**  
- Sensor Ultrassônico → Porta S1
- Sensor Giroscópio → Porta S2
- Sensor de Cor → Porta S3

-----

## 📂 Estrutura do Código
**rotate_sensor_degrees(degrees)**
- Essa função controla o motor responsável pela rotação do sensor ultrassônico. O parâmetro degrees determina o ângulo de rotação, permitindo que o sensor possa medir distâncias à frente, à esquerda ou à direita do robô.
  
**detect_edge()**
- O sensor de cor verifica a reflexão do solo para determinar se há uma borda. Se a reflexão for menor que um certo limiar, significa que o robô está próximo a uma queda, então ele deve parar. Além disso, a função imprime o valor da reflexão na tela do EV3 Brick.
  
**move_fwd_cell()**
- Essa função faz o robô avançar uma célula no grid. Antes de se movimentar, ele verifica se há uma borda usando detect_edge(). Se houver, ele para imediatamente. Caso contrário, ele move 150 mm para frente.
  
**recallibrate()**
- Se o robô perceber que está desalinhado, ele realiza um pequeno recuo seguido de um avanço. Isso ajuda a ajustar sua posição para que continue seguindo corretamente o trajeto.
  
**turn_left() e turn_right()**
- São funções para girar o robô 90° para a esquerda ou para a direita, respectivamente. Elas ajudam na navegação dentro do grid.
**avoid_obstacle_with_analysis()**
- Essa função permite ao robô evitar obstáculos de forma inteligente. Ele para o movimento e usa rotate_sensor_degrees() para medir a distância à esquerda e à direita. Com base na análise dessas distâncias, decide qual direção seguir e executa a rotação correspondente.
  
**continuous_navigation()**

Essa função principal é responsável pela movimentação contínua do robô. Em um loop infinito, ele:

- Verifica bordas usando detect_edge(). Se detectar, ele para e espera.
- Verifica obstáculos com ultra_sonic.distance(). Se um obstáculo estiver próximo, ele usa avoid_obstacle_with_analysis() para decidir a melhor rota.
- Move para frente caso o caminho esteja livre.
  
**main()**
- Essa função inicializa a navegação do robô. Ela limpa a tela do EV3, imprime a mensagem de início e chama continuous_navigation() para executar o movimento e tomar decisões em tempo real.
- 
-----

## 🖥️ Configuração e Execução do Código
**Configure o sistema:**

Instale o ev3dev no LEGO EV3.
Configure o ambiente Python com a biblioteca pybricks.

**Carregue o código:**

Transfira o script ev3_maze.py para o EV3 via SSH ou outro método de sua preferência.

**Prepare o robô:**

Verifique se os motores e sensores estão corretamente conectados conforme a especificação.
Coloque o robô no ponto inicial do grid.

**Execute o código:**

Acesse o terminal do EV3 e execute o comando:
`python ev3_maze.py`

**Acompanhe a navegação:**

Observe as informações exibidas na tela do EV3.
O robô iniciará a navegação autônoma, ajustando sua rota conforme detecta obstáculos ou bordas.

-----
## 🚀 Grupo
Bruno Klein RA: 2201010

Erick Vicentini RA: 2200515

Gabriel Morisco RA:2201686

Guilherme Gimenez RA: 2100786

Guilherme Torres RA: 2200412

Kauã Duque RA: 2201177

Luccas Delgado RA: 2200535

Pedro Henrique RA: 2202159

Ricardo Mantia RA: 2200292

-----

## 🧑‍🏫 Orientador

Projeto desenvolvido sob orientação de [Gustavo Molina](https://github.com/gustavomolina17/gustavomolina17), que contribuiu com apoio técnico e conceitual ao longo da construção do sistema.
