Primera Parte: Script de Jump

Para poder darle salto al personaje comenzamos creando una variable publica de tipo float llamada jumpForce la cual define la intensidad del salto. Se le dio un valor inicial de 5f, pero se puede modificar desde el Inspector de Unity.
Se creo una variable privada de tipo Rigidbody llamada rb. Representa el componente físico del personaje, necesario para aplicar fuerzas y respetar la gravedad.
Y por ultimo, se creo la variable privada de tipo Keyboard llamada keyboard la cual permite detectar cuando se presiona la tecla Space para saltar.

<img width="440" height="347" alt="image" src="https://github.com/user-attachments/assets/cfb4361c-04db-479b-8814-f3c162dc5bb4" />

Luego, en la funcion void start obtenemos la instancia actual del teclado del sistema de entrada lo cual nos permite usar keyboard.spaceKey para detectar el salto. Y en la funcion Awake se obtiene la referencia al Rigidbody que está en el mismo GameObject que este script. Sin esto, no se podria aplicar fuerzas fisicas.

<img width="535" height="347" alt="image" src="https://github.com/user-attachments/assets/372290f8-db6a-4fcd-abc8-92d9f9580562" />

Por último, en la función Update() —que se ejecuta cada frame— implementamos un if cuya condición verifica exactamente cuándo se presionó la tecla Space en este frame específico. Usamos .wasPressedThisFrame (y no .isPressed) para evitar que el salto se repita mientras se mantiene la tecla pulsada, garantizando un salto controlado y realista. Dentro del if ejecutamos: rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse) para poder saltar si la tecla Space fue presionada. El Vector3.up representa la dirección hacia arriba en el eje Y. Se multiplica por jumpForce para controlar la potencia del impulso y ForceMode.Impulse aplica la fuerza instantáneamente, simulando un empujón repentino.

<img width="743" height="325" alt="image" src="https://github.com/user-attachments/assets/60c85e22-b280-481b-a808-a0fd564b31fd" />



Segunda Parte: Script de Sprint

Para implementar el sprint al personaje, comenzamos creando una variable pública de tipo float llamada sprintingMultiplier la cual define el factor de velocidad adicional cuando el jugador corre. Se le dio un valor inicial de 2f, lo que significa que la velocidad se duplica al correr, pero este valor se puede modificar fácilmente desde el Inspector de Unity para ajustar la sensación de velocidad.Se creó una variable privada de tipo float llamada moveSpeed. Esta variable almacena la velocidad actual del personaje en cada momento: ya sea la velocidad normal o la velocidad de sprint. Es el valor que se usa realmente para mover al jugador, permitiendo un control dinámico.Además, se declararo una variable pública de tipo bool: isSprinting que indica si el jugador está corriendo en este momento. 

<img width="415" height="172" alt="image" src="https://github.com/user-attachments/assets/a3756e9e-a209-4d2e-b5aa-cb29320b7b71" />


Luego, en la función void Start() inicializamos moveSpeed con el valor base de speed. Esto asegura que, al comenzar el juego, el personaje se mueva a la velocidad normal por defecto. Sin esta línea, moveSpeed tendría un valor indefinido y el movimiento fallaría.

<img width="416" height="175" alt="image" src="https://github.com/user-attachments/assets/c3557f61-2a61-43e0-915c-28502b92c003" />

Luego, se tuvo que quitar la variable speed dentro de la funcion OnMove la cual estaba siendo multiplicada por el Vector2 ya que movementValue se calculaba una sola vez cuando el jugador presionaba una tecla (WASD). Se multiplicaba por speed (la velocidad base). Pero moveSpeed (que cambia con el sprint) no se usaba aquí. Cuando presionabas Shift mientras te movías, moveSpeed se actualizaba a speed * 2, pero movementValue ya tenía el valor antiguo (solo speed). Lo cual resultaba en que el personaje no acelerara.

<img width="527" height="111" alt="image" src="https://github.com/user-attachments/assets/d3ea2eea-e7ae-4842-8b7a-4b9cca0f32c9" />

Luego en la función Update() —que se ejecuta cada frame— se implementa la lógica principal del sprint con un if-else. La condicion del if: keyboard.leftShiftKey.isPressed. Detecta si la tecla Shift izquierda está siendo mantenida presionada en este frame. Se usa .isPressed porque el sprint debe mantenerse mientras se presiona la tecla, no solo al pulsarla una vez. Si Shift está presionado: isSprinting = true lo cual hace que se multiplique speed con el speedMultiplier y se le asigne el valor de esa multiplicacion a moveSpeed lo cual seria el sprint speed. Si Shift no está presionado: isSprinting = false y el moveSpeed fuese la velocidad normal (speed).

Justo después, se calcula el movimiento ajustado utilizando un vector2. Se crea la variable movementAdjusted la cual se le asigna el valor entre movementValue * moveSpeed. Al multiplicar movementValue por moveSpeed, se obtiene un vector de movimiento con la velocidad correcta (normal o sprint). Este valor se usa en transform.Translate para mover al personaje.

Finalmente, el movimiento se aplica utilizando movementAdjusted.x y movementAdjusted.y como los ejes horizontal y profundidad del movimiento los cuales se multiplican por Time.deltaTime para que el movimiento sea independiente de los FPS.


<img width="607" height="448" alt="image" src="https://github.com/user-attachments/assets/7486b56d-422d-4660-8a42-9d71c5489a24" />
















