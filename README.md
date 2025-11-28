<H1>BOLA NO TUBO</H1>

Este projeto, desenvolvido para a disciplina de Eletrônica Embarcada, consiste em um desenvolvimento de firmware para controlar a posição vertical de uma bola por meio de um fluxo de ar gerado através de uma ventoinha controlada pela abertura ou fechamento de uma válvula acoplada a um motor de passo.

Serão utilizados um sensor óptico refletivo para detecção da abertura total da válvula, um sensor ultrassonico para medição da altura da bola e um sensor de temperatura para compensação da medição da altura da bola. A transmissão e recepção de dados será realizada utilizando uma interface bluetooth que possibilitará a comunicação entre o sistema e o usuário (via celular ou computador).

O firmware desenvolvido será implementado em um microcontrolador PIC16F1827/I-P e utilizadas as ferramentas SNAP, que permite programar e debuggar o código desenvolvido, da Microchip, e um Analisador Lógico de 8 canais para visualização e aferição dos sinais digitais. O diagrama de blocos do projeto está apresentado conforme a Figura 1: <img width="700" height="600" alt="image" src="https://github.com/fernandarmuro/wingardium-levibola/blob/be5bb0134b2ad3a82d7c9f4d4b3726b2a49a7895/Diagrama_de_blocos.png" />


O projeto será dividido em 4 módulos, os quais o desenvolvimento, teste e simulação do código será de responsabilidade individual à cada integrante do grupo. Ao final, cada parte desenvolvida será integrada e testada em um protótipo físico disponibilizado para validadação e verificação do funcionamento do firmware.

O projeto e as atividades de cada integrante seguem a seguinte divisão:

1. Douglas Rodrigues:
   
   - Medição da altura da bola e temperatura.
     
3. Fernanda Muro:
   
   - Comunicação bluetooth.
   
5. Matheus Neves:

   - Controle dos atuadores (ventoinha e válvula).
   
7. Pedro Barros:

   - Algoritmo de controle PID.

O detalhamento de cada módulo desenvolvido no projeto, assim como os arquivos mcc.c e mcc.h de cada um, estão disponíveis nas pastas nominais de cada integrante.

Para uma melhor compreensão geral do projeto, foi elaborada uma máquina de estados finitos para apresentar o funcionamento completo do projeto da bola bola, assim como os estímulos necessários para as transições a saída esperada de cada um.   
