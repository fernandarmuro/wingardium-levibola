<H1>BOLA NO TUBO</H1>

Este projeto, desenvolvido para a disciplina de Eletrônica Embarcada, consiste em um desenvolvimento de firmware para controlar a posição vertical de uma bola por meio de um fluxo de ar gerado através de uma ventoinha controlada pela abertura ou fechamento de uma válvula acoplada a um motor de passo.

Serão utilizados um sensor óptico refletivo para detecção da abertura total da válvula, um sensor ultrassonico para medição da altura da bola e um sensor de temperatura para compensação da medição da altura da bola. A transmissão e recepção de dados será realizada utilizando uma interface bluetooth que possibilitará a comunicação entre o sistema e o usuário (via celular ou computador).

O firmware desenvolvido será implementado em um microcontrolador PIC16F1827/I-P e utilizadas as ferramentas SNAP, que permite programar e debuggar o código desenvolvido, da Microchip, e um Analisador Lógico de 8 canais para visualização e aferição dos sinais digitais. O diagrama de blocos do projeto está apresentado conforme a Figura 1: <img width="700" height="600" alt="image" src="https://github.com/fernandarmuro/wingardium-levibola/blob/be5bb0134b2ad3a82d7c9f4d4b3726b2a49a7895/Diagrama_de_blocos.png" />


O projeto será dividido em 4 módulos, os quais o desenvolvimento, teste e simulação do código será de responsabilidade individual à cada integrante do grupo e, ao final, será integrado e testado em um protótipo físico disponibilizado para validadação e verificação do firmware. 

O projeto e as atividades de cada integrante seguem a seguinte divisão, cujo detalhamento se encontra na pasta nominal de cada integrante:

	1. [Douglas Rodrigues](Douglas/):
	
	- Medição de altura da bola e temperatura.
			
  	2. Fernanda Muro:
	
	- Comunicação bluetooth.
	
  	3. Matheus Neves:

	- Controle dos atuadores (ventoinha e válvula).

	4. Pedro Barros:

	- Algoritmo de controle PID
	
