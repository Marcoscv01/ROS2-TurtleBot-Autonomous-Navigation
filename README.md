Ejercicios para la asignatura de Robots Moviles del master de Robótica y Automatizacion con ROS2 y un Turtlebot.

1. El turtlebot realiza diferentes formas geométricas comom cuadrados y pentágonos haciendo uso de la odometria.
2. El turtlebot avanza hasta encontrar un objeto con el lidar. Tras esto se para.
3. Aparcamiento: El turtlebot avanza hasta encontrar un hueco con su tamaño a la derecha o izquierda, en el cual aparca.


Explicación del aparcamiento:
El código implementa un sistema de aparcamiento automático utilizando un sensor LIDAR para detectar los obstáculos y la odometría para conocer la orientación y posición en todo momento.
En este, se utilizan dos umbrales principales; el umbral frontal y el lateral. Estos valores definen la distancia mínima de seguridad que el robot debe de mantener respecto a los obstáculos detectados por el sensor LIDAR.
Un parámetro importante en el código es el radio, este se utiliza para calcular el ángulo de apertura de los abanicos de detección del LIDAR. El sensor proporciona una lista de 360 medidas y se realiza el análisis de ciertas zonas importantes alrededor del robot dependiendo de su posición.
A partir de los umbrales y el radio, se calculan los abanicos, uno frontal, que analiza las medidas situadas delante del robot, para detectar los objetos frontales, y un abanico lateral, que analiza las medidas del lado correspondiente para comprobar si existe un hueco para aparcar.
El tamaño del abanico depende del ángulo calculado con los umbrales y el valor del radio, para cada ángulo se calcula una distancia límite que se corrige por trigonometría,
El funcionamiento general del robot se controla mediante una máquina de estados, donde cada estado representa una fase del aparcamiento: buscar hueco, girar, entrar, esperar, salir, reorientar el robot y continuar avanzando una vez realizado el aparcamiento.
También en el código se desarrollan reguladores proporcionales que ayudan a ajustar el control angular y lineal.
<img width="1314" height="541" alt="image" src="https://github.com/user-attachments/assets/90ab2d15-42a8-47a4-9b0e-d5e18b4a6cf6" />
