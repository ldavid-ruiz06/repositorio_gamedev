A. El templo mayor

Comenzamos modelando el templo mayor. Como primer paso, creamos un objeto vacío, de forma que podamos interactuar con el templo de manera separada del terreno y de los demás objetos (también porque resulta más organizado).

Base del templo

Iniciamos modelando la forma general del templo con un plano de ProBuilder y lo escalamos por 10 en todo. Usando el eje Z como frente, eliminamos dos caras en cada esquina, de forma que el plano quede así:

<img width="705" height="345" alt="Screenshot 2025-09-25 193058" src="https://github.com/user-attachments/assets/64652295-c828-4921-ac0a-60de045733b3" />

Luego seleccionamos todas las caras y hacemos extrude (0.5) de la superficie. Después escalamos las caras para crear cierto grado de inclinación. Aquí, momentáneamente (su host Jayson) creyó haber encontrado un problema grave. Al venir de Blender, asumí que tendría todas las herramientas disponibles allí, pero ProBuilder parece carecer de la función Inset Faces. Estaba a punto de replantear todo mi enfoque cuando me di cuenta de lo bondadoso que es ProBuilder. Aunque no tenga la función Inset, no permite mostrar el interior hueco de un mesh a menos que se elimine una cara deliberadamente. Es decir, tiene una especie de cinturón de seguridad que evita que ciertas transformaciones revelen el interior.

Así que, sin Inset, lo que hice para simularlo fue:

Seleccionamos todas las caras de la superficie.

Hacemos extrude con distancia 0. Esto separa las caras del mesh, aunque siguen formando parte de él.

Escalamos las caras. Esto debería mostrar el hueco interior, y lo hace, pero solo por unos instantes mientras ProBuilder genera automáticamente las caras que cubren ese espacio.

El resultado es un pseudo-inset:

<img width="881" height="411" alt="Screenshot 2025-09-25 194417" src="https://github.com/user-attachments/assets/4edeb0b1-3f17-4298-90c9-acb020e8223f" />

Repetimos este proceso cuatro veces y obtenemos:

<img width="676" height="399" alt="Screenshot 2025-09-25 195723" src="https://github.com/user-attachments/assets/5e27a248-ee4f-4d4d-a441-ceb8ee9d3176" />

B. Escaleras y detalles

El templo es, y nos quedó, altísimo. Así que hacen falta escaleras para subir. Las creamos a partir de un cubo y un plano.

Primero generamos un plano de ProBuilder y lo posicionamos de la siguiente manera:

<img width="557" height="344" alt="Screenshot 2025-09-25 200737" src="https://github.com/user-attachments/assets/aa5fd869-3e56-4eca-ade7-724cb51462c8" />

Como ProBuilder no parece tener una opción para seleccionar loop cuts, tendremos que dejar de lado las escaleras funcionales y, como en los ejemplos, los personajes tendrán que arreglárselas con escaleras de mano u otros métodos para subir. Para terminar de detallar nuestra pseudoescalera necesitamos tres cubos. Copiamos la rotación del plano anterior y los colocamos así:

<img width="718" height="402" alt="Screenshot 2025-09-25 210147" src="https://github.com/user-attachments/assets/f2f6999d-dc39-4539-9041-b37825a8ad76" />

Hacemos que los cubos de las esquinas sean la mitad de anchos en x. Luego los escalamos para que sean tan largos como las “escaleras”. Finalmente, colocamos un cubo con rotación original al final de cada separador. El resultado debería verse así:

<img width="538" height="355" alt="Screenshot 2025-09-25 210645" src="https://github.com/user-attachments/assets/17022d6f-2f29-4ef8-959c-1273242d4622" />

Los mini-templos de la cima son básicamente mini-pirámides. Podemos tomar cuatro caras superiores y repetir el mismo proceso con el que creamos la base. También podrían modelarse por separado para reutilizarlos en el futuro, pero por razones de tiempo, y porque su host (Jayson) no es particularmente fanático del modelado 3D en Unity, usamos la primera opción.

Agregamos un par de texturas simples al mesh.

El resultado final del templo debería verse:

<img width="709" height="479" alt="Screenshot 2025-09-25 220126" src="https://github.com/user-attachments/assets/47c3d7c1-948c-4dcd-b61c-029a9dec7e6b" />

Debo ser autocrítico y admitir que cometí un error de escala, porque el templo quedó anormalmente grande. Pero eso se resuelve con un ajuste narrativo.

C. Terreno

Creamos un terrain y lo pincelamos ligeramente, ya que se trata de una zona pantanosa. Luego, usando layers, agregamos dos texturas: una de hierba y otra de lodo. Volvemos a pincelar hasta lograr un aspecto convincente.

<img width="771" height="473" alt="Screenshot 2025-09-25 225725" src="https://github.com/user-attachments/assets/6ecf81c1-9c08-4123-a2b8-769fae0eb14a" />

D. Recursos

Agregar personajes no es sencillo, ya que vienen con muchas texturas, rigs y assets. Pero gracias a los poderosísimos ROBOT HEROES contamos con un paquete gratuito que incluye un par de personajes. Así que los añadimos a la escena.

<img width="638" height="382" alt="Screenshot 2025-09-25 230432" src="https://github.com/user-attachments/assets/34779520-5c37-4cc1-9e39-579414d6daa1" />

Y ahora, la historia que enfrentarán nuestros grandiosos ROBOT HEROES es...

Cada 100 años, el gran dios creador Quetzalcoatl, una serpiente emplumada voladora, termina su recorrido por todo el universo, y se dirige al templo Chichén Itzá para completar su recorrido, para luego proceder a empezarlo nuevamente, así en un ciclo que no ha sido interrumpido desde el inicio del tiempo. Se dice que posee poderes incomprensibles para el ser humano, y que sus plumas, verdes y delicadas, son capaces de restaurar el balance perdido de las cosas, ya sea volver terrenos fértiles, devolver el agua a ríos secos, traer la lluvia en desiertos, entre muchas otras cosas. 

Así que en un pequeño pueblo, vivía Yololt, un hombre que ha estado años casado con su mujer. Ambos deseaban empezar una familia, pero luego de varios años sin éxito y una visita a una shaman, ellos aprenden que la esposa era infértil, y que nunca serían capaces de tener hijos. Esto entristece a su mujer. Así que deseando cumplir su sueño de ser padres, Yololt decide ir al templo Chichén Itzá luego de escuchar que el gran Quetzalcoatl está por llegar de su largo viaje, con las intenciones de obtener una de sus milagrosas plumas para curar la infertilidad de su mujer. Sin embargo, al llegar descubre que él no es el único que quiere obtener una pluma, grupos de personas buscando una pizca del poder del dios para resolver sus propios problemas. Y rápidamente encuentran resistencia de parte de los sacerdotes, los cuales no quieren permitir el paso al templo para evitar que las personas se apropien del poder que Quetzalcoatl tiene. 

<img width="1079" height="494" alt="Screenshot 2025-09-25 230706" src="https://github.com/user-attachments/assets/986e2192-4c4b-491f-8ea0-ae01494855e8" />

