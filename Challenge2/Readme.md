Luis D. Ruiz Velázquez

Emanuel Morales

Jayson Sanchez Velázquez

Reto #2: Kirby

Parte 1: Creando el prefab del Kirby

1) Luego de crear y abrir un proyecto nuevo en Unity 3D, empezamos con la creación del prefab de Kirby. Para esto, iniciamos con la creación de una esfera utilizando el menú de 3D objects que ya vienen implementado en el motor. Este será la base para el prefab del modelo. 
<img width="1918" height="589" alt="Screenshot 2025-09-15 201155" src="https://github.com/user-attachments/assets/6b8966c6-5375-4840-94f5-7a48b153e23f" />

2) Luego, utilizando el mismo menú anterior, agregamos un game object de tipo capsula. Esta será utilizada para crear los ojos de Kirby.

<img width="1918" height="629" alt="Screenshot 2025-09-15 201232" src="https://github.com/user-attachments/assets/00dc57cf-4585-4fbf-991b-241bcd866747" />

3) Utilizando una combinación de las herramienta de escala y el inspector, cambiamos las dimensiones de la capsula. Disminuimos la escala en Z para aplanar el objeto, y luego reducimos las escalas en X y Y para reducir el tamaño proporcionalmente para que sean del tamaño correcto. 

<img width="1919" height="620" alt="Screenshot 2025-09-15 201306" src="https://github.com/user-attachments/assets/dd24df9f-e98e-4333-8ded-9bb3932adb8a" />

4) Luego, utilizando la herramienta de movimiento, reposicionamos la capsula a la posición correcta para que sea el ojo derecho de Kirby. 

<img width="1919" height="625" alt="Screenshot 2025-09-15 201733" src="https://github.com/user-attachments/assets/520e6fb7-6c73-4e54-9d0a-6b0d193f1a68" />

5) Después, utilizando el comando de duplicación (Ctrl + D) para duplicar la capsula, y la reposicionamos para hacer el ojo izquierdo de Kirby.

<img width="1919" height="623" alt="Screenshot 2025-09-15 201752" src="https://github.com/user-attachments/assets/5a2261e7-4d66-42fb-95c0-0ae96a5a69f0" />

6) De esta forma, se logra crear el prefab de Kiby simplemente arrastrando el root (un game objet vacio) para crear el prefab de Kirby de manera oficial. Y ahora, podremos utilizar este modelo para crear distintas variaciones de Kirby.

<img width="1919" height="647" alt="Screenshot 2025-09-15 201911" src="https://github.com/user-attachments/assets/056d65b7-7982-4443-9f26-062dbfd3d57c" />

Parte 2: Creando las variantes

Así que con el prefab terminado, procedemos a utilizar este prefab para crear distintas variantes de Kirby. Y para empezar, se creó una variante de Kirby con el copy ability (o poder) de Doctor al que llamaremos Dr. Kirby. 

1) Primero, importamos el prefab creado anteriormente y empezamos añadiendo una esfera. A dicha esfera se le modifican las dimensiones para convertirlas en un circulo. Y a partir de ahí, se acomoda en la parte superior del rostro, de manera que se parezca a la lampara en la frente. 

<img width="1919" height="628" alt="Screenshot 2025-09-15 205321" src="https://github.com/user-attachments/assets/ec1fe57e-f911-4193-b323-3310515442a1" />

2) Luego añadimos dos esferas y se hacen más pequeñas de manera que hagan de las manos de Kirby. 
<img width="1919" height="625" alt="Screenshot 2025-09-15 205519" src="https://github.com/user-attachments/assets/e099fee3-9474-43dd-8a07-b4fbece08028" />

3) Y ya que Dr. Kirby utiliza pociones para combatir los enemigos, agregamos un cilindro y otra esfera, y modificamos sus atributos como el tamaño y posición, de manera que parezcan una poción que Kirby está sosteniendo. 

<img width="1919" height="628" alt="Screenshot 2025-09-15 205738" src="https://github.com/user-attachments/assets/16b22f6a-5a98-4406-93e5-b67d71ea54a5" />

4) Agregamos otra esfera, y nuevamente utilizando la herramienta de escala, cambiamos su tamaño y forma para crear la forma del pie. 

<img width="1919" height="628" alt="Screenshot 2025-09-15 210420" src="https://github.com/user-attachments/assets/a747ec76-cb90-4326-94a5-5ac27e5a2114" />

5) Y una vez tenga la forma deseado, acomodamos el pie para que este debajo de la cabeza en la posición que deseamos. Y nuevamente, lo duplicamos para crear el otro pie, y lo acomodamos según queramos. 

<img width="1919" height="628" alt="Screenshot 2025-09-15 210952" src="https://github.com/user-attachments/assets/10339a83-94d2-4e67-9132-7ad7390d1cf6" />

De esta forma, hemos creado la primera variante utilizando el prefab de Kirby. Así que, utilizando pasos similares pero con distintas figuras, se han creado un total de cuatro variantes utilizando el prefab de Kirby:

Kirby Normal - la forma normal de Kirby, que tiene el poder de comer enemigos y copiar sus poderes. 

<img width="579" height="392" alt="Screenshot 2025-09-15 214123" src="https://github.com/user-attachments/assets/a21a2f79-2915-4570-9e3d-bc0ae2e9ac1a" />

Kirby Mario - la forma que Kirby opta cuando copia la habilidad del famoso fontanero rojo italiano Mario. Esta habilidad puede ser vista en la saga de Super Smash Bro.

<img width="388" height="432" alt="image" src="https://github.com/user-attachments/assets/4a1e1836-e9d2-45d7-bbd8-3e43fe510ad9" />

Kirby Mago - Kirby puede utilizar cartas o trucos clásicos de magia para atacar a los enemigos. Sin embargo, inicialmente, la habilidad Magic solo tenía un uso y al ser utilizada otorgaba un efecto aleatorio que era escogido en una ruleta. 

<img width="375" height="388" alt="image" src="https://github.com/user-attachments/assets/0b5c0ae0-2ccf-4879-a6b2-f878462b8bbc" />


Parte 3: Preparando el terreno

Para crear un heightmap hay muchos métodos. Pero nosotros intentamos, como buenos programadores, usar la forma que menos trabajo manual requiere: enchufar un heightmap y dejar que Unity lo interprete como un terreno.

1) Se crea el RAW file

Primero, como estipulan las instrucciones, vamos a Tangrams y descargamos el heightmap en formato PNG. Unity, sin plugins, solo acepta raw files como imports para crear un terreno.

Aquí se podría pensar en cambiar el formato del archivo desde Files, pero esto lleva a un desastre de terreno. Este problema, asumimos, se debe a que al cambiar el formato a raw desde Files, estás convirtiendo un PNG a raw, con todo y sus canales de colores RGB, canales que Unity no sabe interpretar como heightmaps. Por ello, antes de importar la imagen, hicimos uso de un editor de fotos (Gimp) para convertir este PNG a un grayscale, y de ahí convertirlo a un raw, que pasamos a importar a Unity.

2) Importar el RAW file

Primero creamos el terreno al que importaremos el heightmap con los siguientes ajustes:
<img width="489" height="509" alt="Screenshot 2025-09-16 213627" src="https://github.com/user-attachments/assets/d7b96e67-8491-49bf-ba62-89a9d23ece12" />

Ahora viene lo fácil. Creamos un terreno en Unity y, en la pestaña de ajustes del terreno, importamos el raw heightmap. Aquí pueden, y surgieron, varios problemas, todos ellos culminando en este bloque de púas aterrador:
<img width="780" height="409" alt="Screenshot 2025-09-15 223641" src="https://github.com/user-attachments/assets/fd7fbb29-0c47-4ff1-a2df-7dbaac1fc6f1" />

Uno de estos problemas puede ser la resolución del raw file. Si el raw file tiene un tamaño muy dispar con el del terreno, Unity parece intentar comprimir el heightmap para que quepa, llevando al error. Lo mismo si la resolución es muy pequeña; Unity estira el raw file para que abarque todo el terreno, dejándolo con apenas elevaciones. Si este es el problema, jugar con la resolución del terreno de Unity y del raw file parece poder arreglarlo.

Exportamos el heightmap con los siguientes ajustes.

<img width="405" height="585" alt="Screenshot 2025-09-16 213706" src="https://github.com/user-attachments/assets/6a3403aa-300a-47aa-9563-4c6b6669bdce" />

3) Una vez el raw es procesado, se crear el terrain a partir del heightmap

<img width="1919" height="626" alt="Screenshot 2025-09-16 213817" src="https://github.com/user-attachments/assets/3fd426ca-d889-43a3-98d0-b3533ad04081" />

Y mira qué lindo. De seguro esculpirlo hubiera sido más rápido que trastear con esta magia, pero el sentimiento de haber automatizado el proceso sin duda lo vale. Aunque parece tener un error en el borde, en donde una pared gigante se alza, tras las incontables abominaciones creadas, culparemos de esto a la forma en la que Gimp convirtió el PNG a raw.

Ahora, los kirbys comienzan a planear su conquista:

<img width="628" height="465" alt="image" src="https://github.com/user-attachments/assets/389112b0-3074-4d6c-83cb-e7eacf913b59" />

Tras tanto esfuerzo, nisiquiera un hroe tan poderoso como ROBOT HERO puede detener a las bolas de odio rosadas.

<img width="908" height="540" alt="Screenshot 2025-09-16 221149" src="https://github.com/user-attachments/assets/32b478ae-c8ce-47f1-819c-d231fe75fb42" />


Historias personales:

Emanuel Morales:

Mi unica experiencia con Kirby fue jugando Super Smash Bros en mi Nintendo 3DS. Recuerdo jugar con mis amigos en la escuela, cada uno con su personaje diestro. El mio era Greninja, pero Kirby era el de mi amigo. Siempre agarraba y comia a mi Greninja o terminaba volando por el mapa por un martillazo de Kirby.

Luis D. Ruiz

Kirby siempre ha sido un personaje bastante icónico para mí, gracias a su adorable y su habilidad de copiar los poderes de los enemigos, mecánica que me parece bastante divertida y única. Aunque no he podido jugar mucho de sus juegos, los que he podido jugar me han parecido bien entretenidos, en especial cuando los juegos en conjunto con mi familia o amigos. Así que Kirby siempre será un personaje especial para mí. 

Jayson Sánchez:

No crecí con consolas de Nintendo, y ahora de grande no tengo dinero para comprar videojuegos para una. Pero tengo memorias especiales relacionadas a Kirby. Como gran juego de fiestas que es, jugaba mucho Super Smash Bros en casas y consolas ajenas, como la de mi tío. Como malos jugadores, nos divertíamos aplastando botones, puro corazón, nada de mente. Pero la cosa dejaba de ser divertida cuando las victorias se empiezan a acumular de un solo lado, situación que siempre involucraba... a uno de los dos usando a Kirby. Como lo de mal perdedor parece fluir en la familia, las humillantes derrotas y agridulces victorias usando a Kirby son lo primero que me viene a la mente al pensar en el personaje.
