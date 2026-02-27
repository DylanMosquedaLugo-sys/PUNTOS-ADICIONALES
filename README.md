# PUNTOS-ADICIONALES
Introducción:
Este simulador de memoria es una herramienta interactiva con una estética retro-arcade diseñada para visualizar cómo un sistema operativo gestiona y asigna espacio a diferentes programas. Este simulador permite experimentar con la creación de bloques de memoria y colas de procesos. A través de su interfaz, puedes observar en tiempo real cómo se comportan dos algoritmos clásicos de asignación de memoria, evaluando su eficiencia y el desperdicio de espacio que generan.
Instrucciones   ¿qué significan los resultados?)
¿Qué debe hacer el usuario?
Para utilizar el simulador, debes seguir estos pasos en el panel de control:
Ingresa el tamaño en KB y presiona "[+] INSERTAR BLOQUE" para configurar los cartuchos o bloques de memoria disponibles.
Ingresa el tamaño en KB y presiona "[+] INSERTAR PROCESO" para encolar los programas que necesitan ser ejecutados.
Selecciona "INICIAR P1 (BEST FIT)" o "INICIAR P2 (WORST FIT)" para ejecutar la simulación con el algoritmo deseado.
Utiliza los botones de "[X] BORRAR" o "!! REINICIO TOTAL !!" para limpiar la memoria, la cola o reiniciar toda la actividad.
¿Qué va a observar?
Durante la ejecución, la interfaz visual te mostrará lo siguiente:
Un mapa de memoria donde los bloques se llenan visualmente según el tamaño de los procesos asignados.
Una leyenda de colores donde el negro representa espacio libre, el color cyan representa espacio asignado y el rojo anaranjado advierte sobre la fragmentación o basura.
La cola de procesos, cuyos elementos se volverán grises y transparentes a medida que el sistema intente asignarlos a la memoria.
Un indicador de texto que muestra el progreso, cambiando de "EJECUTANDO..." a "FINALIZADO".
¿Qué significan los resultados?Al terminar la simulación, aparecerá un panel de "MISIÓN COMPLETADA" con las siguientes estadísticas:EstadísticaSignificadoMODOIndica el algoritmo que se utilizó para la simulación, ya sea "MEJOR AJUSTE" o "PEOR AJUSTE".PUNTAJE (ÉXITO)Representa la cantidad total de procesos que el sistema logró acomodar exitosamente en los bloques de memoria.GAME OVER (FALLOS)Muestra la cantidad de procesos que no pudieron ser asignados porque no había ningún bloque con espacio suficiente para ellos.DESPERDICIO (FRAG)Es la suma en KB del espacio sobrante (fragmentación interna) dentro de los bloques que tienen al menos un proceso asignado.NIVEL EFICIENCIAEs el porcentaje de memoria realmente utilizada en relación con la capacidad total de todos los bloques configurados.
Explicación de los algortimos:
El simulador implementa dos estrategias fundamentales para decidir en qué bloque de memoria debe colocarse un proceso:
P1 - Mejor Ajuste (Best Fit): Este algoritmo evalúa todos los bloques de memoria disponibles y selecciona aquel que tenga el espacio restante más pequeño que sea suficiente para albergar el proceso. Su objetivo es dejar el menor espacio libre posible en el bloque elegido.
P2 - Peor Ajuste (Worst Fit): A diferencia del anterior, este algoritmo busca entre todos los bloques disponibles y selecciona el que tenga la mayor cantidad de espacio restante. La intención detrás de esta estrategia es que el espacio sobrante sea lo suficientemente grande como para poder alojar otros procesos en el futuro.
Reflexión:El simulador demuestra visualmente que no existe una solución perfecta para la asignación de memoria; cada algoritmo tiene ventajas y desventajas dependiendo de los procesos que lleguen. El "Mejor Ajuste" es excelente para optimizar bloques específicos, pero a menudo genera fragmentos sobrantes tan pequeños (fragmentación) que resultan inútiles para futuros procesos. Por otro lado, el "Peor Ajuste" parece contraintuitivo al buscar el espacio más grande, pero al hacerlo, los fragmentos restantes suelen ser lo suficientemente amplios como para ser aprovechados por procesos más pequeños que lleguen después. La elección del algoritmo en un sistema operativo real depende en gran medida del tamaño promedio de los programas y de la frecuencia con la que entran y salen de la memoria.
Cláusula de uso de IA:
Nombre del Estudiante: Dylan Emmanuel Mosqueda Lugo.
IA utilizada: Gemini.
Fecha: 2026/02/27
propósito: para cambiarle el estilo al codigo.
prompt: ponle el  estilo que tiene
Archivos adjuntos: fue un html con nombre de algoritmos.
respuesta de la IA: 

Gemini ha dicho
Para aplicar el estilo Retro-Arcade de 8 bits que tiene tu simulador de memoria a otros elementos o proyectos, aquí tienes los componentes clave extraídos directamente de tu archivo algoritmos.html.

1. Paleta de Colores Neón
La identidad visual se basa en contrastes altos sobre fondos oscuros:

Fondo: #1a002b (Morado muy oscuro)

Principal: #39ff14 (Verde Neón Terminal)

Acento 1: #00ffff (Cyan)

Acento 2: #ff00ff (Magenta)

Alerta: #ff3300 (Rojo naranja)

2. Tipografía y Efectos de Texto
Para lograr el "look" de consola antigua, utiliza la fuente VT323 de Google Fonts.

CSS
font-family: 'VT323', monospace;
text-transform: uppercase;
/* Efecto Glitch en títulos */
text-shadow: 3px 3px 0px #ff00ff, -3px -3px 0px #00ffff;
3. Estética de Pantalla CRT (Scanlines)
El "filtro" de monitor viejo se logra con un gradiente repetido que simula las líneas de refresco:

CSS
body::after {
    content: "";
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(
        0deg,
        rgba(0, 0, 0, 0.2),
        rgba(0, 0, 0, 0.2) 2px,
        transparent 2px,
        transparent 4px
    );
    pointer-events: none;
    z-index: 999;
}
4. Componentes UI (Botones y Paneles)
Bordes de Píxel: En lugar de bordes suaves, usa bordes sólidos de 4px con sombras sólidas (sin desenfoque) para dar profundidad.

Botones "Presionables": Tienen una sombra que desaparece al hacer clic para simular el movimiento físico del botón:

CSS
button {
    border: 4px solid;
    box-shadow: 4px 4px 0px #000;
    position: relative;
    top: 0;
}
button:active {
    top: 4px;
    box-shadow: 0px 0px 0px #000;
}
5. Contenedores de Memoria (Visualización)
Los bloques de memoria usan un fondo negro con una rejilla verde tenue y barras de carga que se llenan con colores sólidos. La "fragmentación" se representa con un patrón de líneas diagonales de advertencia.

¿Te gustaría que aplique este estilo visual a algún otro fragmento de código específico que tengas?
