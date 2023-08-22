# Controle E Automação De Um Manipulador Robótico Com Sensor De Força


## 1. Introdução
Robôs industriais estão, cada vez mais, auxiliando operadores humanos em realizações de tarefas em locais confinados, perigosos e inclusive operações cirúrgicas. O projeto consiste no controle de posição e força de um manipulador robótico, explorando conceitos de cinemática direta, inversa e controle de força baseado no erro de posição, implementados em linguagem de programação Python e Arduino.

<img src="https://github.com/felipecacique/BracoRobotico/blob/main/img/fluxograma.png" />

## 2. Referencial teórico
### 2.1 Cinemática Inversa
Cinemática inversa é uma ferramenta para calcular os ângulos entre as hastes de um objeto articulado em função da sua coordenada espacial. Isso é feito por meio de equações trigonometricas obtidas através de transformadas espaciais (método matricial), ou trigonometria. Existem várias combinações de ângulos possíveis para uma mesma coordenada. 
𝑥,𝑦,𝑧 = f(θ_1, θ_2, ..θ_𝑛)

<img src="https://github.com/felipecacique/BracoRobotico/blob/main/img/cinematica_inversa.png" />

### 2.2 Controle de força
Foi construído um dispositivo constituindo de uma tesoura, potenciômetro e servo motor, para controle de ângulo e força da garra do manipulador. Foi implementado o “controle direto de reflexão da força” (DFR), relativamente simples mas que possui uma boa performance. 
A fórmula de controle é:
- 𝐹𝑒𝑒𝑑𝑏𝑎𝑐𝑘 𝑑𝑒 𝐹𝑜𝑟ç𝑎 = 𝑒𝑟𝑟𝑜 𝑑𝑒 𝑝𝑜𝑠𝑖çã𝑜 𝑥 𝑔𝑎𝑛ℎ𝑜
- 𝑒𝑟𝑟𝑜 𝑑𝑒 𝑝𝑜𝑠𝑖çã𝑜 = θ_𝑎𝑡𝑢𝑎𝑙 − θ_𝑒𝑛𝑣𝑖𝑎𝑑𝑜

### 2.3 Sensor de força
Quando uma força é realizado sobre um material, este sofre uma deformação, retornando à posição de equilíbrio após a retirada da carga (regime elástico). Sensores como Strain Gage variam sua tensão de acordo com sua deformação. Baseando-se neste princípio, o sensor de flexão desenvolvido por Machado (2016) foi adaptado em uma nova configuração, funcionando da seguinte maneira: Uma tensão realizada deforma o tubo de silicone, diminuindo proporcionalmente a luminosidade incidente do Led emissor sobre o receptor, ambos posicionados nas extremidades. Pode-se facilmente converter a tensão elétrica do receptor em unidade de força.

<img src="https://github.com/felipecacique/BracoRobotico/blob/main/img/feedback_forca.png" />

## Resultados e conclusão
O sensor de força utilizado apresentou repetitividade e uma sensibilidade de carga aproximadamente na faixa de 100g a 1200kg. O método de “controle direto de reflexão da força” (DFR) implementado também apresentou uma boa performance tendo em vista a simplicidade e precisão dos componentes envolvidos. Visualmente o manipulador repetiu os movimentos realizados pelo usuário, e através de testes do robô carregando diferentes objetos, foi possível controlar a força aplicada. Por fim, foi feita a automação do manipulador, no qual ele realiza repetitivamente uma tarefa programada pelo dispositivo construído.
