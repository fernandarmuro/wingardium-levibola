<H1>BOLA NO TUBO</H1>

Este projeto consiste em um sistema de aquisição de dados e controle da altura de uma bola
que flutua dentro de um tubo vertical pela ação de um fluxo de ar. O fluxo de ar é gerado por uma
ventoinha e pode ser controlado mudando o ciclo útil do sinal de alimentação da ventoinha ou pela
abertura ou fechamento de uma válvula acoplada a um motor de passo.

Um sensor óptico refletivo (TCRT-5000) detecta abertura total da válvula, permitindo inicializar sua
posição. Este sensor entrega um valor analógico de tensão, sendo mínimo quando o sinal luminoso
não reflete na válvula, indicando que está totalmente aberta. Em qualquer outra posição, onde o
sensor estiver tampado pela válvula e o sinal seja refletido, o valor de tensão será máximo por
conta da queda de tensão no resistor R3 e da condução do optotransitor que o sensor possui na
sua saída.

Outro sensor (HC-SR04) possibilita medir a altura da bola, emitindo um sinal de ultrassom que
impacta contra a bola e retorna para o sensor. O tempo de voo do sinal permite calcular a distância
entre o sensor e a bola. Mas, a velocidade do som muda com a temperatura e por isso se utiliza
um sensor de temperatura (LM35) para compensar a medição de altura.

Uma interface Bluetooth permite o envio e recepção de dados entre o sistema e um celular ou um
computador. Um microcontrolador PIC16F1827/I-P, alimentado com 5V, controla todo o sistema.
O sistema também possui um programador SNAP da Microchip e um Analisador Lógico de 8 canais,
que permitem programar e debuggar o firmware e visualizar os sinais digitais envolvidos.

Objetivo final conforme a imagem:<img width="875" height="740" alt="image" src="https://github.com/user-attachments/assets/14256940-2174-4fa8-963d-095cd81767e7" />
