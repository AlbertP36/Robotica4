# Primer proyecto "Doblete intermitente" : esta hecho con el simulador de Arduino en Tinkercad.

Consiste en dos diodos led que se tienen que encender simultáneamente en un lapso de 1 segundo en un bucle , en este programa también usamos dos resistencias de 220 Ω para protegerlos , para el montaje necesitamos una placa protoboard y se ponen los componentes sobre ella , se conectan los cables primero se conecta GND (Con un cable negro a poder ser) el cable GND tiene que estar debajo de el segundo diodo LED y el resto de cables se ve como se colocan en la imagen de abajo. 

<img width="1074" height="468" alt="image" src="https://github.com/user-attachments/assets/2f4b3c29-e681-4580-a0c2-7f0e591bf402" />

En este ejercicio trabajamos estos scripts : Void Setup y Void Loop - Se usan para estructurar un programa , Void setup se usa para decirle a un programa lo que tiene que hacer al iniciarse para luego dar paso al loop , en este caso en el setup le damos corriente a los pines 12 y 13 (También se puede dar el imput para recibir datos ).En void loop se pone básicamente el programa para que se ejecute en bucle.
Delay - Delay se usa para que el programa espere antes de su siguiente acción.
Digital Write - Digital write se usa para dar ordenes a los pines y ponerlos en High o Low por ejemplo.


# Segundo proyecto "Pulsador" : esta hecho con el simulador de Arduino en Tinkercad.

Consiste en una estructura principal de un pulsador , que cuando se aprieta , apaga el LED , si no el LED esta encendido en este programa también usamos resistencias de 220 Ω para proteger el montaje y los cables van conectados como se ve abajo en la foto pero como novedad se usa un cable para el pin de 5V para darle energía a el pulsador.

<img width="897" height="455" alt="image" src="https://github.com/user-attachments/assets/566012ad-1e4e-4c2d-9f3d-bdd76af50526" />
 
En este ejercicio trabajamos estos scripts : -  #Define para definir una variable , Int que se usa también para definir una variable de tipo entero, If es una estructura condicional que funciona algo así : Es un "SI" , (Ej) si este pulsador esta encendido apago la luz etc.

# Tercer proyecto " Potenciómetro. Monitor serie." : esta hecho en físico.

Esta practica consiste en usar un potenciómetro para ver en el portátil el valor que marca , el potenciómetro es un dispositivo que se puede rotar para subir o bajar el valor que marca , marca valores decimales asique se usan pines analógicos para su lectura , los potenciómetros pueden ser útiles por ejemplo para controlar la intensidad de algo como por ejemplo el volumen que produce un altavoz o la intensidad de una pistola de masajes.

<img width="448" height="280" alt="image" src="https://github.com/user-attachments/assets/bcea4ab8-2eec-4083-8e88-e07652472faf" />

https://www.youtube.com/watch?v=u_LzLcUyPQk

En esta practica usamos los scripts - Float , es una variable que puede tener valores decimales - Serialbegin y Serialprintnl , se usan para mostrar valores en la pantalla del ordenador - AnalogRead , para leer valores en los pines Analógicos.

# Cuarto proyecto "Mapeado de datos del potenciómetro." : esta hecho en físico.

Esta practica es igual que la anterior en montaje y prácticamente en código pero se usa el script del mapeado.

<img width="465" height="302" alt="image" src="https://github.com/user-attachments/assets/3cbacaf1-ab31-4c0e-8b3c-6b8313dec1e0" />

https://www.youtube.com/watch?v=FqHJXZcOIXY

Aquí usamos solo el script de el mapeado que consiste : En que dos valores diferentes sean equivalentes quitando así los números decimales y estos se aproximan.

# Quinto proyecto "PWM" : esta hecho en físico.

En esta practica hay que usar un  potenciómetro para controlar la intensidad de una luz LED, también se usa una resistencia de 220 Ω.

<img width="925" height="407" alt="image" src="https://github.com/user-attachments/assets/f2177929-98a9-46b6-9fd7-9363f10cb4ce" />

https://www.youtube.com/watch?v=ZORLppsyEgE

En esta practica no se usan scripts nuevos (creo).

# Reto no guiado 1:

Esta practica es la fusión de todos los anteriores proyecto usando un poco de cada uno , consiste en controlar el brillo de 5 diodos LED haciendo que cuando uno se encienda totalmente el siguiente comience a iluminarse y en reversa para ello se usan 5 diodos una resistencia el potenciómetro y bastantes cables y resistencias.

(Foto C)

<img width="4000" height="2250" alt="20261023_115924" src="https://github.com/user-attachments/assets/ab5c1f0a-ee23-4a5c-9cb3-fc404b4b9eaa" />

https://www.youtube.com/watch?v=Mg_up4jKXAc

En este proyecto no se usan scripts nuevos se usan todos los vistos hasta el momento.














# CODIGO MAPEADO 

int lecturapoten = 0;
int potenciometro = A0;
long result = 0;
String rx_str = "";

void setup() {
  Serial.begin(9600);
}

void loop() {
  if (Serial.available() > 0) {
    rx_str = Serial.readStringUntil('\n');
    result = map(rx_str.toInt(), 2, 38, 6, 42);
  }

  lecturapoten = analogRead(potenciometro);
  Serial.println(lecturapoten);
  delay(1000);





