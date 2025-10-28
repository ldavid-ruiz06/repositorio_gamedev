Primera Parte: Script de Jump

Para poder darle salto al personaje comenzamos creando una variable publica de tipo float llamada jumpForce la cual define la intensidad del salto. Se le dio un valor inicial de 5f, pero se puede modificar desde el Inspector de Unity.
Se creo una variable privada de tipo Rigidbody llamada rb. Representa el componente físico del personaje, necesario para aplicar fuerzas y respetar la gravedad.
Y por ultimo, se creo la variable privada de tipo Keyboard llamada keyboard la cual permite detectar cuando se presiona la tecla Space para saltar.

<img width="440" height="347" alt="image" src="https://github.com/user-attachments/assets/cfb4361c-04db-479b-8814-f3c162dc5bb4" />

Luego, en la funcion void start obtenemos la instancia actual del teclado del sistema de entrada lo cual nos permite usar keyboard.spaceKey para detectar el salto. Y en la funcion Awake se obtiene la referencia al Rigidbody que está en el mismo GameObject que este script. Sin esto, no se podria aplicar fuerzas fisicas.

<img width="535" height="347" alt="image" src="https://github.com/user-attachments/assets/372290f8-db6a-4fcd-abc8-92d9f9580562" />

Por último, en la función Update() —que se ejecuta cada frame— implementamos un if cuya condición verifica exactamente cuándo se presionó la tecla Space en este frame específico. Usamos .wasPressedThisFrame (y no .isPressed) para evitar que el salto se repita mientras se mantiene la tecla pulsada, garantizando un salto controlado y realista. Dentro del if ejecutamos: rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse) para poder saltar si la tecla Space fue presionada. El Vector3.up representa la dirección hacia arriba en el eje Y. Se multiplica por jumpForce para controlar la potencia del impulso y ForceMode.Impulse aplica la fuerza instantáneamente, simulando un empujón repentino.

<img width="743" height="325" alt="image" src="https://github.com/user-attachments/assets/60c85e22-b280-481b-a808-a0fd564b31fd" />








