<H1>COMINUCAÇÃO BLUETOOTH</H1>

Para o projeto bola no tudo, será implementado um sistema de comunicação serial e assíncrono por meio do módulo externo HC-05, capaz de estabelecer conexões via bluetooth Serial Port Protocol (SSP) e o módulo periférico Enhanced Universal Syncronous Asyncronous Receiver Trasmitter (EUSART) do PIC16F1827 através dos pinos Tx e Rx para o envio e recepção dos dados de controle entre o protótipo e um dispositivo externo (celular ou computador).

Na Figura 1, está apresentado o esquemático do módulo HC-05 e as conexões Tx e Rx com o módulo bluetooth J2.

<div align="center">
  
  <img src="DB_CBT.png" alt="Diagrama da FSM do Bola no Tubo" width="500"/> 
  
  <em>Figura 1: Esquemático do HC-05 e conexões Tx e Rx.</em>
  
</div>
Na figura 2, está apresentando o PIC16F1827 com as conexões Tx e Rx nos pinos RB1 e RB2.
<div align="center">
  
  <img src="PIC16F1827.png" alt="Diagrama da FSM do Bola no Tubo" width="600"/> 
  
  <em>Figura 1: Diagrama de blocos do projeto bola no tubo.</em>
  
</div>

<H2>Comunicação serial <H2>
