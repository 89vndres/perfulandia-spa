# perfulandia-spa
Aplicación "Perfulandia" (Mi Evaluación EP3)

1. ¿Qué es esto?

Caso: Perfulandia (una tienda de perfumes).
Objetivo: Esta es mi app para la Evaluación Parcial 3. Hice una aplicación que cumple con todo lo que se pidió:

Se ve bien y es fácil de usar.

Tiene un login que no te deja avanzar si no escribes nada.

Te muestra un "cargando..." cuando espera al servidor.

Guarda cosas en el teléfono (como el carrito y tu sesión).

Usa funciones del teléfono (la cámara y el GPS).

Se conecta a un servidor de verdad para el login.

2. ¿Qué usé para hacerla?

Lenguaje: Kotlin (¡obvio!).

Diseño: Vistas de Android de toda la vida (XML).

Para no colgar la app: Usé Corutinas para las tareas pesadas (como llamar a la API o guardar en la base de datos).

Para hablar con el servidor (API): Usé Retrofit, que es la herramienta estándar para esto.

Para el carrito: Usé Room, que es una base de datos en el teléfono. Así el carrito no se borra aunque cierres la app.

Para las funciones del celu: Usé las herramientas de Google (Play Services) para el GPS y los ActivityResultContracts para la cámara.

¿Cómo la pruebas?

Clonas el proyecto.

Lo abres con Android Studio (uno reciente, ojalá).

Le das al botón "Play" (Run 'app') en un emulador o tu teléfono.

Importante: Necesitas un usuario y contraseña que ya existan en la API de Xano para poder entrar.

3. ¿Cómo está ordenada la app?

Para que sea fácil de entender, la ordené así:

LoginActivity.kt / MainActivity.kt: Son las dos pantallas (el login y la tienda).

ApiService.kt: Aquí está toda la configuración para conectarse al servidor (la "dirección" de la API, qué datos enviar, etc.).

BaseDeDatos.kt: Aquí se define la base de datos del carrito.

Perfume.kt: Un archivo simple para guardar la info de un perfume.

¿Cómo funciona por dentro?

Estado: Cuando le das a "Ingresar", aparece una ruedita de "cargando" y el botón se bloquea. Si el servidor da error, te lo digo con un mensaje (un Toast).

Sesión: Cuando entras, guardo un "token" (como un ticket de acceso) en los SharedPreferences del teléfono.

Navegación: La app siempre parte en el Login. Si entras bien, te llevo a la Tienda (MainActivity) y destruyo la pantalla de Login para que no puedas volver a ella con el botón "atrás".
