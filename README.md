<H1>BOLA NO TUBO</H1>

Este projeto, desenvolvido para a disciplina de Eletrônica Embarcada, consiste em um desenvolvimento de firmware para controlar a posição vertical de uma bola por meio de um fluxo de ar gerado através de uma ventoinha controlada pela abertura ou fechamento de uma válvula acoplada a um motor de passo. São utilizados sensores ópticos refletivo para detecção da abertura total da válvula e medição da altura da bola para calcular a altura da bola. Para correção de possíveis erros associados a medida da altura da bola, é utilizado um sensor de temperatura. Para a transmissão e recepção de dados entre o sistema e o usuário (computador ou celular), é utilizada uma interface bluetooth. 

Todo o firmware será desenvolvido para o microcontrolador PIC16F1827/I-P, alimentado com 5V. O sistema possui um programador SNAP da Microchip e um Analisador Lógico de 8 canais,
para programar e debuggar o firmware e visualizar os sinais digitais.


Objetivo final conforme a imagem:<img width="700" height="600" alt="image" src="https://github.com/fernandarmuro/wingardium-levibola/blob/be5bb0134b2ad3a82d7c9f4d4b3726b2a49a7895/Diagrama_de_blocos.png" />


O projeto foi realizado por 4 alunos do curso de engenharia eletronica, dividido nas respectivas pasta com os nomes e tendo como as devidas atividades desenvolvidas:
<ul>
  <li>DOUGLAS: Medição de altura da bola</li>
  <li>FERNANDA: Comunicação serial-BT</li>
  <li>MATHEUS: Movimento do motor de passo e detecção do fim de curso</li>
  <li>PEDRO: Controle PI ou PID</li>
</ul>
