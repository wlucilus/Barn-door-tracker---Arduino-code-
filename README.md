# Barn-door-tracker---Arduino-code-  (instrucoes em portugues abaixo)
Arduino code to controls a step motor 28byj 48 using a driver Uln2003. 

Based on the 200mm barn door tracker project adapted from    
https://github.com/aglomeradoaberto/barn_door_tracker ,  
https://www.youtube.com/watch?v=P_qqLA0WKJg , https://tinyurl.com/30tracker
https://www.cyber-omelette.com/2016/10/manual-barn-door-tracker.html

There is also a code for the 3D printed star tracker project:  
https://www.instructables.com/Equatorial-Mount-for-DSLR/


___

Calculations:

$$ \text{Earth rotation (star rotation in our points of view)} = 360 degrees / 24 h  = 360 / (60*24) min = 0.25 degrees/min  $$

Or in rad ($rad = 2\pi/360 degree$) this becomes 

$$ \omega_{earth} = 2 \pi / 60*24 = 0.00463 rad /min $$

Now, $\omega_{earth}$ is the angular velocity of the door, i.e, how fast the door should be openning. 

The upparward (tangencial) door velocity is $V = r \omega_{earth}$ that for a 200mm axis ( axis is 20cm away from hinge)

$$ V = r_{axis} \omega_{earth} = 200*0.00463 = 0.872664626 mm/min $$

On the other hand the tangencial velocity is controled by rod thread and gear revolution. For a thread of 0.8mm, this means that it will raise 0.8mm every gear revolution.
Therefore we would need approximately one revolution per minute to match the tangencial velocity of need for a point at the door 200mm away from the hinge.

If we use gear reduction, than the velocity of the motor should be increased by the gear factor, which is the ration of gear threads (or ratio of gear radius).
In a  8:1 reduction, motor velocity should be approx. 8 times per minute.

PS: In my case, I used rule of threes to get the axis gear to turn one revolution per minute, as this stepper library gives the velocity in strange numbers....

---
# Codigo de arduino para Barn door tracker Arduino
Codigo de arduino para controlar o motor de passo 28byj 48 usando um dirver Uln2003

Com base no projeto do seguidor de estrelas de porta de celeiro de 200mm adaptado de
https://github.com/aglomeradoaberto/barn_door_tracker , https://www.youtube.com/watch?v=P_qqLA0WKJg , https://tinyurl.com/30tracker

Também há um código para o projeto do rastreador de estrelas 3D impresso:
https://www.instructables.com/Equatorial-Mount-for-DSLR/


___

Calculos:

$$ \text{Rotacao da terra(rotacao das estrelas no nosso referencial)} = 360 graus / 24 h   = 360 / (60*24) min = 0.25 graus/min  $$

Ou usandando radiano ($rad = 2\pi/360 degree$) 

$$ \omega_{terra} = 2 \pi / 60*24 = 0.00463 rad /min $$

Agora, $\omega_{terra}$ devera ser a velocidade angular da porta, i.e, o quao rapido a porta deve abrir. 

A velocidade tangencial (para cima) de um ponto da porta sera $V = r \omega_{earth}$, que para um ponto a 200mm do dobradica se torna

$$ V = r_{eixo} \omega_{terra} = 200*0.00463 = 0.872664626 mm/min $$

Por outro lado, a velocidade tangencial é controlada pela passo de rosca do eixo metalico e pela revolução da engrenagem. Para uma rosca de 0,8mm, isso significa que ela subirá 0,8mm a cada revolução da engrenagem.
Portanto, precisaríamos de aproximadamente uma revolução por minuto para corresponder à velocidade tangencial necessária para um ponto na porta a 200mm da dobradiça.

Se usarmos uma redução de engrenagem, a velocidade do motor deve ser aumentada pelo fator da engrenagem, que é a razão das roscas da engrenagem (ou a razão do raio da engrenagem).
Em uma redução de 8:1, a velocidade do motor deve ser aproximadamente 8 vezes por minuto.

Obs: No meu caso, fiz regra de tres com a velocidade do motor, ate obter uma revolucao por minuto da engrenagem do eixo.









  
